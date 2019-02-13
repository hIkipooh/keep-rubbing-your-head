<template>
  <v-app>
    <v-container fluid grid-list-md>
      <v-layout row justify-space-between>
        <v-flex md2 left-right color="black">
          <navbar-left />
        </v-flex>
        <v-flex>
          <text-and-c-l />
        </v-flex>
        <v-flex md2 left-right>
          <index-right />
        </v-flex>
      </v-layout>
    </v-container>
  </v-app>
</template>

<script>
import NavbarLeft from "./components/NavbarLeft.vue";
import TextAndCL from "./components/TextAndCL.vue";
import IndexRight from "./components/IndexRight.vue";

export default {
  name: "App",
  components: {
    "navbar-left": NavbarLeft,
    "text-and-c-l": TextAndCL,
    "index-right": IndexRight
  }
  // data: () => ({
  //   user: [
  //     {
  //       example1: [
  //         "Hello there.",
  //         "The angel from my nightmare, the shadows in the background of the morgue.",
  //         "The unsuspecting victim. Of the darkness in the valley we can live like Jack and Sally if we want.",
  //         "Where you can always find me."
  //       ]
  //     },
  //     {
  //       example2: [
  //         "This is an example, where we can find some complexity.",
  //         "The thing about essays structured like this is that they probably didn't think it through beforehand",
  //         {
  //           theUnsuspected: [
  //             "But then again, how can you call it a file structure if there are no nested directories?",
  //             {
  //               codeCoffee: [
  //                 "The lessone here is guys, if you are struggling with code coffee, take three days to assign yourself some code coffee because nobody can torture you more than you can torture yourself ^오^"
  //               ]
  //             }
  //           ]
  //         }
  //       ]
  //     }
  //   ],
  //   currentDirectory: [],
  //   pathDictionary: [],
  //   scope: "directory"
  // })
};
</script>

<style>
.left-right {
  height: 100%;
  width: 100%;
  border-style: solid;
  border-color: #76ff03;
  border-width: 10px;
}
.text {
  color: #76ff03;
}
</style>
