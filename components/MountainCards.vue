<template>
  <!-- NOTE: This component is the equivalent of Debbie's ProductCard component in the video -->
  <div>
    <button @click="$fetch" class="text-sm bg-blue-500 hover:bg-blue-700 text-white font-bold p-2 rounded-full mb-4">Refresh</button>

    <p v-if="$fetchState.pending">Fetching Mountains</p>
    <p v-else-if="$fetchState.error">An Error Occured</p>

    <div v-for="currentMountain in mountainsArr" v-bind:key="currentMountain.title" class="mb-8 flex justify-start text-left items-center">
      <div class="md:flex-shrink-0">
        <img v-bind:src="currentMountain.image" alt="Who cares" class="rounded-lg md:w-56">
      </div>
      <div class="mt-4 md:mt-0 md:ml-6">
        <div class="uppercase tracking-wide text-sm text-indigo-600 font-bold">
          {{currentMountain.continent}}
        </div>
        <a href="#" class="block mt-1 text-lg leading-tight font-semibold text-gray-900 hover:underline">
          {{currentMountain.title}}
        </a>
        <p class="mt-2 text-gray-600">
          {{currentMountain.description}}
        </p>
      </div>
    </div>
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