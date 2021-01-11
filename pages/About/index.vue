<template>
  <div>
    <div class="container">
      <h2 class="title">About</h2>
      <h3>Je vais utilier cette page pour tester les nuxt connection helpers</h3>
      <!-- NOTE: il est vraiment simple que ça dessous. -->
      <p v-if="$nuxt.isOffline">Vous êtes hors-ligne </p>
      <p v-else-if="$nuxt.isOnline">Ayyee. t'es en-ligne 👍🏿. Que neuf ?</p>
      <div>
        <nuxt-link to="/">Home</nuxt-link>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  created() {
    //  NOTE: it seems as if this logs this vue component page
    // TODO: take a look around at this and study it
    console.log(this.$nuxt);
  },
};
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
}
</style>