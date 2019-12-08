<template>
  <b-container>
    <b-row align-v="center">
      <b-col cols="4" class="text-right">Generator</b-col>
      <b-col>
        <b-form-select v-model="generator" :options="generatorOptions" />
      </b-col>
    </b-row>
  </b-container>
</template>

<script lang="ts">
import { Component, Prop, Vue, Watch } from 'vue-property-decorator';
import { generators, AreaGenerator, capitalize, RecursiveBacktracker, Field, generator } from 'amazer';
import { AmazerState } from "../views/Home.vue";

@Component
export default class GeneratorConfig extends Vue {

  sharedState = AmazerState;

  generator: AreaGenerator<any> = RecursiveBacktracker;

  get generators(): Array<[AreaGenerator<any>, Field[] | undefined]> {
    return generators();
  }

  get generatorOptions(): string[] {
    let options = [];
    for (let entry of this.generators) {
      options.push({text: capitalize(entry[0].name), value: entry[0]});
    }
    return options;
  }

  @Watch("generator")
  forwardGenerator() {
    this.sharedState.generator = {generator: this.generator};
  }
}
</script>