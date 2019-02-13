<template>
  <v-app>
    <v-textarea
      class="main"
      v-model="mainText"
      ref="mainText"
      disabled
    ></v-textarea>
    <v-textarea
      class="command-log"
      v-model="commandLog"
      ref="commandLog"
      readonly
    ></v-textarea>
    <v-text-field
      class="command-line"
      v-model="commandText"
      v-on:keyup.enter="onEnter"
    ></v-text-field>
  </v-app>
</template>

<script>
export default {
  name: "TextAndCL",
  props: ["user", "currentDirectory", "pathDictionary", "scope"],
  data: () => ({
    commandText: "",
    commandLog: "",
    mainText: ""
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
      const path = dir.split("/");
      const traverse = (key, element) => {};
      for (const i = 0; i < path.length; i++) {
        this.user.forEach(el => {
          for (const key in el) {
            if (key === path[i]) {
              this.currentDirectory = this.user[i];
            } else {
              traverse(path[i], el);
            }
          }
        });
      }
    },
    convertDirectory: function() {
      let directory = this.user[this.currentDirectory[0]];
      for (const i = 1; i < this.currentDirectory.length; i++) {
        directory = directory[this.currentDirectory[i]];
      }
      return directory;
    },
    list: function() {},
    pwd: function() {
      console.log("=====currentDirectory========", this.convertDirectory());
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

<style>
.main {
  width: 100%;
  height: 70%;
  color: black;
}
.command-log {
  width: 100%;
  height: 20%;
  background-color: grey;
}
.command-line {
  width: 100%;
  height: 10%;
}
</style>
