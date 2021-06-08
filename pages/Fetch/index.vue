<template>
  <div class="mountains-container">
    <div v-for="currentMountain in mountainsArr" v-bind:key="currentMountain.title" class="mb-8 flex justify-start text-left items-center">
      <div class="md:flex-shrink-0">
        <img v-bind:src="currentMountain.image" alt="Who cares" class="rounded-lg md:w-56">
      </div>
      <div class="mt-4 md:mt-0 md:ml-6">
        <div class="uppercase tracking-wide text-sm text-indigo-600 font-bold">
          {{currentMountain.continent}}
        </div>

        <NuxtLink v-bind:to="`/fetch/${currentMountain.slug}`" class="block mt-1 text-lg leading-tight font-semibold text-gray-900 hover:underline">
          {{currentMountain.title}}
        </NuxtLink>
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
  async asyncData() {
    const API = "https://api.nuxtjs.dev/mountains";

    const mountains = await fetch(API)
      .then((response) => {
        console.log(response);
        return response.json();
      })
      .then((data) => {
        console.log(data); // expect this to be the same output as console.log(mountains) below
        return data;
      })
      .finally(() => {
        console.log("passed or failed, here we are");
      });

    console.log(mountains);

    return {
      mountainsArr: mountains,
    };
  },
};
</script>

<style>
.mountains-container {
  width: 90%;
  margin: 0 auto;
}
img {
  height: 120px;
}
</style>

// NOTE: not done. I'll be back