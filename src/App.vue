<template>
  <v-app>
    <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>Farsi</span>
        <span class="font-weight-light">numbers</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn flat to="/">Home</v-btn>
      <v-btn flat to="/about">About</v-btn>
    </v-toolbar>
    <v-content>
      <router-view/>
    </v-content>
  </v-app>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
@Component({}) // Component としての作成は必須
export default class App extends Vue {}
</script>
