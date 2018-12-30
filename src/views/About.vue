<template>
  <div class="about">
    <v-container>
      <v-layout text-xs-center wrap>
        <v-flex xs12>
          <p class="font-weight-bold mb-3 display-3">فارسی</p>
        </v-flex>
      </v-layout>
    </v-container>
    <HelloWorld msg="Welcome to Vue.js + TypeScript App"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src

@Component({
  components: {
    HelloWorld,
  },
})
export default class About extends Vue {}
</script>
