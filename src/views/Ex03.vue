<template>
  <div class="ex">
    <input type="text" v-model.number.lazy="num1" />+
    <input type="text" v-model.number.lazy="num2" />=
    {{ answer }}
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class XXXComponent extends Vue {
  private num1 = 0;
  private num2 = 0;

  //   private answer = 0;

  get answer(): number {
    return this.num1 + this.num2;
  }
}
</script>

<style scoped></style>
