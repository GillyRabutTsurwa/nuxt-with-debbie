<template>
  <div class="container mx-auto mt-8 px-4 flex-col">
    <h1>Mountains</h1>
    <LazyMountainCards v-if="show" />
    <button @click="showMountains" class="text-sm bg-blue-500 hover:bg-blue-700 text-white font-bold p-2 rounded-full mb-4">Show Mountains</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false,
    };
  },
  methods: {
    showMountains() {
      this.show = true;
    },
  },
};
</script>