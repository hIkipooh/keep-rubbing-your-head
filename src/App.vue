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
    essay: [[]],
    currentDirectory: ""
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
