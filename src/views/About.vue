<template>
  <div class="about">
    <v-container>
      <v-layout text-center wrap>
        <v-flex xs12>
          <p class="font-weight-bold mb-3 display-3">فارسی</p>
        </v-flex>
      </v-layout>
    </v-container>
    <hello-world />
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

@Component({
  components: {
    HelloWorld,
  },
})
export default class About extends Vue {
}
</script>