<template>
  <div>
    <p>yo. Everything works well. if you can see the id below</p>
    <p>let me finish, if the id matches with the route path in the URL</p>
    <p> This is id number: {{id}} </p>
  </div>
</template>

<script>
export default {
  async asyncData(context) {
    //NOTE: just as a reminder, we don't have access to "this" to access our vue instance, so we can't obtain our params as usual using this.$route.params.id, we have to get it from the context object that is the principal arugment of the asyncData()
    // NOTE: but i will use destructuring. so insted of this code below:
    // const $axios = context.$axios;
    // const params = context.params;
    // console.log(params);
    // NOTE: i will do this
    const { $axios, params } = context;
    const id = params.id;

    const response = await $axios.$get(`https://api.nuxtjs.dev/posts/${id}`);
    console.log(response);
    // n'oublier pas a renvoyer ce que tu veux utiliser dans notre appli tant que tes données. des que renvoyé, nos données peuvent être utlisées comme d'habitude (dans notre template HTML, dans notre hooks, etc)
    return {
      id: id,
    };
  },
  created() {
    console.log(this);
    console.log(this.params);
  },
};
</script>

<style>
</style>