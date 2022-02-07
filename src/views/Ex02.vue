<template>
  <div class="test">
    <div>名前：{{ name }}</div>
    <div>年齢：{{ age }}歳</div>
    <div>10年後の年齢：{{ futureAge }}歳</div>
    趣味：<span v-for="hobby of hobbies" v-bind:key="hobby"
      >{{ hobby }}&nbsp;</span
    >
    <div><a v-bind:href="url">ラクスパートナーズ株式会社</a></div>
    <div><img v-bind:src="imgUrl" /></div>
    <button type="button" v-on:click="onclick" v-bind:disabled="canNotClick">
      ボタン
    </button>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class XXXComponent extends Vue {
  private name = "";
  private age = 0;
  private futureAge = 0;
  private hobbies = new Array<string>();
  private url = "";
  private imgUrl = "";
  private canNotClick = false;

  onclick(): void {
    this.name = "山田太郎";
    this.age = 31;
    this.futureAge = this.age + 10;
    this.hobbies = ["スイム", "バイク", "ラン"];
    this.url = "https://www.rakus-partners.co.jp/";
    this.imgUrl = "img/hegdhog.jfif";
    this.canNotClick = true;
  }
}
</script>

<style scoped>
.test {
  text-align: left;
  border: 4px solid;
  display: inline-block;
}
</style>
