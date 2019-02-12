<template>
  <v-app>
    <v-container fluid grid-list-xl>
      <v-layout row justify-space-between>
        <v-flex xs2 left-right color="black">
          <navbar-left />
        </v-flex>
        <v-flex>
          <text-and-c-l />
        </v-flex>
        <v-flex xs2 left-right>
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
  },
  data: () => ({
    essay: [
      [
        "this is the sample.",
        "this is the sample to test your life.",
        "how you gon do me like that bruh"
      ],
      [
        "The hack are you talking about I didn't do anything.",
        "Well that ain't good for no nothing.",
        "Do not disrespect the programmer."
      ],
      [
        "What the hack are you going to do about it.",
        "I don't really think that I'm going to do anything about it my fellow brotherling."
      ],
      ["Go about your merry way then."]
    ],
    currentDirectory: [1, 2],
    scope: "block"
  })
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
