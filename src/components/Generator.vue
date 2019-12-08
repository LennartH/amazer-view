<template>
  <b-container>
    <b-row class="mt-2">
      <b-col cols="3"><SizeConfig id="area-size" /></b-col>
      <b-col cols="5"><GeneratorConfig /></b-col>
      <b-col></b-col>
      <b-col cols="1"><b-button variant="dark" @click="generate">Generate</b-button></b-col>
    </b-row>
  </b-container>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import SizeConfig from "@/components/SizeConfig.vue";
import GeneratorConfig from "@/components/GeneratorConfig.vue";
import { generators, capitalize, AreaGenerator } from "amazer";

@Component({
  components: {
    SizeConfig, GeneratorConfig
  }
})
export default class Generator extends Vue {
  generator: string = "RecursiveBacktracker";

  get generatorOptions(): string[] {
    let generatorNames = [];
    for (let entry of generators()) {
      const generator: AreaGenerator<any> = entry[0];
      generatorNames.push(capitalize(generator.name));
    }
    return generatorNames;
  }

  generate() {
    console.log("Generate!");
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
