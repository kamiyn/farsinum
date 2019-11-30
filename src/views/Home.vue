<template>
  <div class="home">
    <FarsiNumber />
  </div>
</template>

<script lang="ts">
// @ is an alias to /src
import FarsiNumber from "@/components/FarsiNumber.vue";

export default {
  name: "home",
  components: {
    FarsiNumber,
  },
};
</script>
