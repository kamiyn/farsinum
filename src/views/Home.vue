<template>
  <div>
    <FarsiNumber />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import FarsiNumber from "@/components/FarsiNumber.vue"; // @ is an alias to /src

@Component({
  components: {
    FarsiNumber,
  },
})
export default class Home extends Vue {}
</script>
