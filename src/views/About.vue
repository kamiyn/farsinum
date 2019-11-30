<template>
  <div class="about">
    <v-container>
      <v-layout text-xs-center wrap>
        <v-flex xs12>
          <p class="font-weight-bold mb-3 display-3">فارسی</p>
        </v-flex>
      </v-layout>
    </v-container>
    <hello-world />
  </div>
</template>

<script lang="ts">
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "about",
  components: {
    HelloWorld,
  },
};
</script>