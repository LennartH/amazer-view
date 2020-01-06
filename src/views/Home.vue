<template>
  <div class="home">
    <AmazerView />
  </div>
</template>

<script lang="ts">
import AmazerView from "@/components/AmazerView.vue";
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
    AmazerView
  }
}
</script>
