<template>
  <div class="home">
    <Generator />
  </div>
</template>

<script lang="ts">
import Generator from "@/components/Generator.vue";
import { Dict, RecursiveBacktracker } from "amazer";


export const AmazerState: Dict<any> = {
    size: {width: 15, height: 15},
    generator: {generator: RecursiveBacktracker},
    modifiers: [],
    area: undefined,
    areaText: ""
};

export default {
  name: 'home',
  components: {
    Generator
  }
}
</script>
