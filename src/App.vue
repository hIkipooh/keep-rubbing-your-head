<template>
  <v-app>
    <navbar-left />
    <text-and-c-l />
    <index-right />
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
  data() {
    return {
      //
    };
  }
};
</script>
