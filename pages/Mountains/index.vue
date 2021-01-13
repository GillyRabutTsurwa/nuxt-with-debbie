<template>
  <div class="container mx-auto mt-8 px-4">
    <div>
      <nuxt-link to="/">Back Home</nuxt-link>
    </div>
    <ProductCard v-for="currentMountain in mountainsArr" v-bind:key="currentMountain.title" v-bind:mountainObj="currentMountain" class="mb-4" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      mountainsArr: [],
    };
  },
  async fetch() {
    const response = await fetch("https://api.nuxtjs.dev/mountains");
    const data = await response.json();
    console.log(data);
    this.mountainsArr = data;
  },
};
</script>

<style>
.container {
  width: 90%;
}
img {
  height: 120px;
}
</style>