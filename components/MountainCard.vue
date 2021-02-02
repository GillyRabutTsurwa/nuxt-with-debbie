<template>
  <div class="md:flex">
    <div class="md:flex-shrink-0">
      <img v-bind:src="mountain.image" alt="Who cares" class="rounded-lg md:w-56">
    </div>
    <div class="mt-4 md:mt-0 md:ml-6">
      <div class="uppercase tracking-wide text-sm text-indigo-600 font-bold">
        {{mountain.continent}}
      </div>
      <a href="#" class="block mt-1 text-lg leading-tight font-semibold text-gray-900 hover:underline">
        {{mountain.title}}
      </a>
      <p class="mt-2 text-gray-600">
        {{mountain.description}}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    mountainObj: {
      type: Object,
      required: true,
      default: () => {},
    },
  },
  data() {
    return {
      mountain: this.mountainObj,
    };
  },
};
</script>

<style>
</style>