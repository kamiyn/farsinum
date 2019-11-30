<template>
  <div class="home">
    <FarsiNumber />
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";
// @ is an alias to /src
import FarsiNumber from "@/components/FarsiNumber.vue";

@Component({
    components: {
    FarsiNumber,
  },
})
export default class Home extends Vue {
}
</script>
