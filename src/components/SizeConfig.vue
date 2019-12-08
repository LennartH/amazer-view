<template>
  <b-container :id="id">
    <b-row align-v="center" no-gutters>
      <b-col cols="2" class="text-right pr-2">Size</b-col>
      <b-col cols="4">
        <b-form-input v-model.number="sharedState[stateKey].width" :id="`${id}-width`" type="number" min="1" size="sm" style="text-align: right;" placeholder="width" />
      </b-col>
      <b-col cols="2" class="text-center text-monospace">x</b-col>
      <b-col cols="4">
        <b-form-input v-model.number="sharedState[stateKey].height" :id="`${id}-height`" type="number" min="1" size="sm" placeholder="height" />
      </b-col>
    </b-row>
  </b-container>
</template>

<script lang="ts">
import { Component, Prop, Vue, Watch } from 'vue-property-decorator';
import { Dict } from 'amazer';
import { AmazerState } from "../views/Home.vue";

@Component
export default class SizeConfig extends Vue {
  @Prop() private id!: string;
  @Prop() private stateKey!: string;

  sharedState = AmazerState;
}
</script>