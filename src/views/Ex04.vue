<template>
  <div class="ex">
    <input type="text" v-model.number="num1" /><br />
    <input type="text" v-model.number="num2" /><br />
    <input type="text" v-model.number="num3" />
    <div>税抜き価格：{{ subTotal.toLocaleString() }}円</div>
    <div>税込み価格：{{ includingTax.toLocaleString() }}円</div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class XXXComponent extends Vue {
  private num1 = 0;
  private num2 = 0;
  private num3 = 0;
  private tax = 0.1;

  get subTotal(): number {
    return this.num1 + this.num2 + this.num3;
  }
  get includingTax(): number {
    return Math.floor(this.subTotal + this.subTotal * this.tax);
  }
}
</script>

<style scoped></style>
