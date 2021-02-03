<template>
  <div>
    <h1>Mountains</h1>
    <!-- Instead of <MountainList/> it is now <LazyMountainList/>. Simple que ça, on a desormais un composant automatique -->
    <LazyMountainList v-if="show" />
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