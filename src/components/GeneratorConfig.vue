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
import { Component, Prop, Vue } from 'vue-property-decorator';
import { generators, AreaGenerator, capitalize, RecursiveBacktracker } from 'amazer';

@Component
export default class GeneratorConfig extends Vue {

  generator: string = capitalize(RecursiveBacktracker.name);

  get generatorOptions(): string[] {
    let generatorNames = [];
    for (let entry of generators()) {
      const generator: AreaGenerator<any> = entry[0];
      generatorNames.push(capitalize(generator.name));
    }
    return generatorNames;
  }
}
</script>