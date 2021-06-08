<template>
  <div class="container mx-auto">
    <div class="relative py-16 bg-white overflow-hidden">
      <NuxtLink to="/fetch">Back</NuxtLink>
      <div class="relative px-4 sm:px-6 lg-px-8">
        <div class="text-lg max-w-prose mx-auto mb-6">
          <p class="text-base text-center leading-6 text-indigo-600 font-semibold tracking-wide uppercase">
            {{mountain.continent}}
          </p>
          <h1 class="mt-2 mb-8 text-3xl text-center leading-8 font-extrabold tracking-tight text-gray-900 sm:text-4xl sm:leading:10">{{mountain.title}}
          </h1>
        </div>
        <figure>
          <img v-bind:src="mountain.image" v-bind:alt="mountain.title" class="w-auto h-auto rounded-lg mx-auto">
          <figcaption class="text-center">{{mountain.title}}</figcaption>
        </figure>
        <div class="prose prose-lg text-gray-500 mx-auto">
          <ul>
            <li><span class="font-bold">Height:</span>{{mountain.height}}</li>
            <li><span class="font-bold">Country:</span>{{mountain.countries[0]}}</li>
          </ul>
          <p>{{mountain.description}}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData(context) {
    /*
    console.log(context);
    const params = context.params;
    console.log(params);
    console.log(params.slug);
    const $axios = context.$axios;
    console.log($axios);
    */

    // au lieu de celui dessûs (refreshing my javascript here)
    const { params, $axios } = context;

    const mountain = await $axios.$get(`https://api.nuxtjs.dev/mountains/${params.slug}`);
    console.log(mountain);
    return {
      mountain: mountain,
    };
  },
};
</script>

<style>
svg {
  width: 2rem;
  height: 2rem;
  display: inline-block;
}
</style>