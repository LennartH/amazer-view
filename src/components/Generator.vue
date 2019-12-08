<template>
  <div>
    <b-container>
      <b-row class="mt-3" no-gutters>
        <b-col cols="3"><SizeConfig id="area-size" stateKey="size" /></b-col>
        <b-col cols="4"><GeneratorConfig /></b-col>
        <b-col></b-col>
        <b-col cols="1"><b-button variant="dark" block class="px-1" @click="generate">Generate</b-button></b-col>
      </b-row>
    </b-container>
    <b-container :fluid="true">
      <b-row class="mt-2 bg-dark text-white" no-gutters><Area /></b-row>
    </b-container>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import SizeConfig from "@/components/SizeConfig.vue";
import GeneratorConfig from "@/components/GeneratorConfig.vue";
import Area from "@/components/Area.vue";
import amazer, { generators, capitalize, AreaGenerator, Size, AreaModifier, RecursiveBacktracker, Config, GeneratorWithConfig, ModifierWithConfig, areaToString, Dict } from "amazer";
import { AmazerState } from "../views/Home.vue";


@Component({
  components: {
    SizeConfig, GeneratorConfig, Area
  }
})
export default class Generator extends Vue {
  generate() {
    let config = new Config(AmazerState.size, AmazerState.generator, AmazerState.modifiers);
    let area = amazer(config).generate();
    AmazerState.areaText = areaToString(area);
  }
}
</script>