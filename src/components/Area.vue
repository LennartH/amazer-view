<template>
  <b-container :fluid="true">
    <b-row class="align-items-center area-text text-center text-monospace">
      <b-col class="p-0">{{ sharedState.areaText }}</b-col>
    </b-row>
  </b-container>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import { AmazerState } from "../views/Home.vue";

@Component
export default class AreaView extends Vue {
  sharedState = AmazerState;

  textareaRows: number = this.sharedState.size.height;
}
</script>

<style scoped>
.area-text {
  white-space: pre;
  overflow: auto;
  line-height: 19px;

  height: 100vh;
  max-height: 85vh;
}
</style>