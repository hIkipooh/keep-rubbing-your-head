<template>
  <div id="app">
    <v-app id="inspire">
      <v-container fluid fill-width>
          <v-card class="main title font-weight-medium" v-model="mainText">

          </v-card>
            <v-textarea
              class="main title font-weight-medium"
              v-model="mainText"
              disabled
            ></v-textarea>
            <v-textarea
              class="command-log title font-weight-light"
              v-model="commandLog"
              readonly
            ></v-textarea>
          <v-text-field
            class="command-line title font-weight-light"
            v-model="commandText"
            v-on:keyup.enter="onEnter"
          ></v-text-field>
      </v-container>
    </v-app>
  </div>
</template>

<script>
export default {
  name: "TextAndCL",
  props: [],
  data: () => ({
    commandText: "",
    commandLog: "",
    mainText: "",
    user: [
      {
        example1: [
          "Hello there.",
          "The angel from my nightmare, the shadows in the background of the morgue.",
          "The unsuspecting victim. Of the darkness in the valley we can live like Jack and Sally if we want.",
          "Where you can always find me."
        ]
      },
      {
        example2: [
          "This is an example, where we can find some complexity.",
          "The thing about essays structured like this is that they probably didn't think it through beforehand",
          {
            theUnsuspected: [
              "But then again, how can you call it a file structure if there are no nested directories?",
              {
                codeCoffee: [
                  "The lessone here is guys, if you are struggling with code coffee, take three days to assign yourself some code coffee because nobody can torture you more than you can torture yourself ^오^"
                ]
              }
            ]
          }
        ]
      }
    ],
    currentDirectory: [],
    pathDictionary: [],
    scope: "directory"
  }),
  methods: {
    onEnter: function() {
      const commands = ["cd", "pwd", "ls", "insert", "change", "delete"];
      const inputCommand = this.commandText.split(" ");
      const commandAction = inputCommand[0];
      if (!commands.includes(commandAction)) {
        this.commandLog +=
          "==========Please enter correct command=========== \n";
        this.commandText = "";
        return console.log("==========Not a Command===========");
      }
      inputCommand.shift();
      switch (commandAction) {
        case "cd":
          this.changeDirectory(inputCommand);
          break;
        case "pwd":
          this.pwd();
          break;
        case "ls":
          this.list();
          break;
      }
      this.commandText = "";
    },
    changeDirectory: function(dir) {
      const path = dir[0].split("/");
      const traverse = (key, element) => {
        for (const key2 in element) {
          if (key2 === key) {
            this.currentDirectory = element[key2];
          }
        }
      };
      for (let i = 0; i < path.length; i++) {
        this.user.forEach(el => {
          for (const key in el) {
            if (key === path[i]) {
              this.currentDirectory = el;
            } else if (typeof el[key] !== "string") {
              traverse(path[i], el);
            }
          }
        });
      }
      console.log("=======current directory========", this.currentDirectory);
      console.log("============path========", path);
    },
    convertDirectory: function() {
      let directory = this.user[this.currentDirectory[0]];
      for (const i = 1; i < this.currentDirectory.length; i++) {
        directory = directory[this.currentDirectory[i]];
      }
      return directory;
    },
    list: function() {
      this.commandLog += JSON.stringify(Object.keys(this.currentDirectory));
    },
    pwd: function() {
      const convertCurrentDirectory = Object.keys(this.currentDirectory);
      this.commandLog += convertCurrentDirectory;
    },
    setUpPathDictionary: function() {
      this.pathDictionary = [];
      this.pathDictionary.push(Object.keys(this.user));
    }
  }
  //   created: function() {
  //   }
};
</script>

<style></style>
