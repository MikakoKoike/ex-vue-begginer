<template>
  <div class="test">
    <div>名前：{{ name }}</div>
    <div>年齢：{{ age }}歳</div>
    <div>10年後の年齢：{{ age + 10 }}歳</div>
    趣味：
    <span v-for="hobby of hobbies" v-bind:key="hobby">{{ hobby }}&nbsp;</span>

    <div><a v-bind:href="url">ラクスパートナーズ株式会社</a></div>
    <div><img v-bind:src="imgUrl" /></div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class XXXComponent extends Vue {
  private name = "山田太郎";
  private age = 31;
  private hobbies = ["スイム", "バイク", "ラン"];
  private url = "https://www.rakus-partners.co.jp/";
  private imgUrl = "img/hegdhog.jfif";
}
</script>

<style scoped>
.test {
  text-align: left;
  border: 4px solid;
  display: inline-block;
}
</style>
