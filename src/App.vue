<template>
  <div id="app">
  <v-app id="inspire">
    <v-navigation-drawer
      fixed
      clipped
      class="grey lighten-4"
      app
      v-model="drawer"
    >
      <v-list
        dense
        class="grey lighten-4"
      >
        <template v-for="(item, i) in items">
          <v-layout
            row
            v-if="item.heading"
            align-center
            :key="i"
          >
            <v-flex xs6>
              <v-subheader v-if="item.heading">
                {{ item.heading }}
              </v-subheader>
            </v-flex>
            <v-flex xs6 class="text-xs-right">
              <v-btn small flat>edit</v-btn>
            </v-flex>
          </v-layout>
          <v-divider
            dark
            v-else-if="item.divider"
            class="my-3"
            :key="i"
          ></v-divider>
          <v-list-tile
            :key="i"
            v-else
            @click=""
          >
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title class="grey--text">
                {{ item.text }}
              </v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </template>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar color="amber" app absolute clipped-left>
      <v-toolbar-side-icon @click.native="drawer = !drawer"></v-toolbar-side-icon>
      <span class="title ml-3 mr-5">Google&nbsp;<span class="text">Keep</span></span>
      <v-text-field
        solo-inverted
        flat
        label="Search"
        prepend-icon="search"
      ></v-text-field>
      <v-spacer></v-spacer>
    </v-toolbar>
    <v-content>
      <v-container fluid fill-height class="grey lighten-4">
        <v-layout justify-center align-center>
          <text-and-c-l />
        </v-layout>
      </v-container>
    </v-content>
  </v-app>
</div>
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
</style>
