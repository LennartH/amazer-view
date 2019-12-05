<template>
  <div class="generator">
    <h1>{{ msg }}</h1>
    <div class="config">
      <div class="size">
        Size
        <input v-model.number="width" type="number" placeholder="w" class="size-input">
        x
        <input v-model.number="height" type="number" placeholder="h" class="size-input">
      </div>
      <div>
        Generator
        <select v-model="generator">
          <option v-for="option in generatorOptions" :key="option">
            {{ option }}
          </option>
        </select>
      </div>
      <button @click="generate">Generate</button>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import { generators, capitalize, AreaGenerator } from "amazer";

@Component
export default class Generator extends Vue {
  @Prop() private msg!: string;

  width: number = 10;
  height: number = 10;
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
    // console.log("Generate!");
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.size-input {
  width: 40px;
}
</style>
