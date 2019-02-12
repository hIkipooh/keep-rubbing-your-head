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
  props: ["essay", "currentDirectory", "scope"],
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
      if (!commands.includes(commandAction) || inputCommand.length > 2) {
        this.commandLog +=
          "==========Please enter correct command=========== \n";
        // this.$refs.commandLog.value = "=====Invalid command=====";
        this.commandText = "";
        return console.log("==========Not a Command===========");
      }
      console.log(inputCommand);
      console.log(commandAction);
      this.commandText = "";
    },
    insert: function() {
      const directory = currentDirectory.split("/");
    },
    changeDirectory: function(dir) {
      //   let directory = dir.slice(3, string.length - 1);
      //   directory = directory.split("/");
    }
  }
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
