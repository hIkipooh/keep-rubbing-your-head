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
        <v-list dense class="grey lighten-4">
          <template v-for="(item, i) in items">
            <v-layout row v-if="item.heading" align-center :key="i">
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
            <v-list-tile :key="i" v-else @click="">
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
        <v-toolbar-side-icon
          @click.native="drawer = !drawer"
        ></v-toolbar-side-icon>
        <span class="title ml-2 mr-3"
          >Damn&nbsp;<span class="text">It</span></span
        >
        <v-text-field
          solo-inverted
          flat
          label="Search"
          prepend-icon="search"
        ></v-text-field>
        <v-spacer></v-spacer>
      </v-toolbar>
      <v-content>
        <v-layout>
          <v-flex xs12>
            <text-and-c-l />
          </v-flex>
        </v-layout>
      </v-content>
    </v-app>
  </div>
</template>

<script>
import TextAndCL from "./components/TextAndCL.vue";

export default {
  name: "App",
  components: {
    "text-and-c-l": TextAndCL
  }
};
</script>

<style></style>
