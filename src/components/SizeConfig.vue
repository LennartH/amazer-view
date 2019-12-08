<template>
  <b-container :id="id">
    <b-row align-v="center" :no-gutters="true">
      <b-col cols="2" class="text-right pr-2">Size</b-col>
      <b-col cols="4">
        <b-form-input v-model.number="width" :id="`${id}-width`" type="number" size="sm" style="text-align: right;" placeholder="width" />
      </b-col>
      <b-col cols="2" class="text-center text-monospace">x</b-col>
      <b-col cols="4">
        <b-form-input v-model.number="height" :id="`${id}-height`" type="number" size="sm" placeholder="height" />
      </b-col>
    </b-row>
  </b-container>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class SizeConfig extends Vue {
  @Prop() private id!: string;

  width: number = 10;
  height: number = 10;
}
</script>