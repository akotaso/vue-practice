<template>
  <div class="container">
    <div v-on:click="cssAnime()">cssAnime{{ count }}</div>
    <router-link to="page">リンク</router-link>
    <div
      v-if="active === true"
      v-on:click="pageSwich()"
      v-bind:class="{ hinge: bom }"
      class="page1 animated"
    >{{ msg }}</div>
    <div v-if="active === false" v-on:click="pageSwich()" class="page2 animated flipInX">ページ2</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      msg: "こんにちは",
      active: true,
      bom: false,
      count: null
    };
  },
  methods: {
    pageSwich() {
      if (this.active === true) {
        this.active = false;
      } else {
        this.active = true;
      }
    },
    cssAnime() {
      this.count += 1
      if (this.count % 5 === 0) {
        this.bom = true;
      } else {
        this.bom = false;
      }
    }
  }
};
</script>

<style>
.page1 {
  width: 500px;
  height: 500px;
  background-color: aqua;
}
.page2 {
  width: 500px;
  height: 500px;
  background-color: rgb(255, 106, 130);
}
</style>
