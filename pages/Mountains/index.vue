<template>
  <div class="container mx-auto mt-8 px-4 flex-col">
    <div>
      <nuxt-link to="/">Back Home</nuxt-link>
    </div>

    <p v-if="$fetchState.pending">Fetching Mountains</p>
    <p v-else-if="$fetchState.error">An Error Occured</p>

    <ProductCard v-else v-for="currentMountain in mountainsArr" v-bind:key="currentMountain.title" v-bind:mountainObj="currentMountain" class="mb-8 justify-start text-left items-center" />
    <!-- This $fetch function, which is embedded in nuxt, refreshes the data retrieved using the fetch() (remember, this is nuxt fetch not regular js fetch), but not the page itself. You can console.log() this funciton in the created hook to see its content. But this is very easy and self explanatory. -->
    <button @click="$fetch">Refresh</button>
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
  created() {
    console.log(this.$fetchState);
    // console.log(this.$fetch); // I see, this fetch() is a promise. So it's literally a way of re running the fetch process. It seems to me that this function returns a promise. Will comment it out. Was just curious to see what was in here
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