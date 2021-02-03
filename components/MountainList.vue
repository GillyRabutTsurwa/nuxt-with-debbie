<template>
  <div class="container mx-auto mt-8 px-4 flex-col">
    <div>
      <NuxtLink to="/">Back Home</NuxtLink>
    </div>
    <button @click="$fetch" class="text-sm bg-blue-500 hover:bg-blue-700 text-white font-bold p-2 rounded-full mb-4">Refresh</button>

    <p v-if="$fetchState.pending">Fetching Mountains</p>
    <p v-else-if="$fetchState.error">An Error Occured</p>

    <MountainCard v-for="currentMountain in mountainsArr" v-bind:key="currentMountain.title" v-bind:mountainObj="currentMountain" class="mb-8 justify-start text-left items-center" />
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