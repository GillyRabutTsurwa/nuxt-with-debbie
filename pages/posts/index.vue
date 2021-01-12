<template>
  <div>
    <h4>All my posts go here</h4>
    <div class="posts-container">
      <div v-for="currentPost in posts" v-bind:key="currentPost.id" class="post border-4 border-solid border-green-400">
        <h5>Mountain Name: {{currentPost.title}}</h5>
        <h6> {{currentPost.height}} </h6>
        <p> {{currentPost.description}} </p>
        <nuxt-link v-bind:to="`/posts/${currentPost.id}`">More Info</nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData(context) {
    const $axios = context.$axios;
    const posts = await $axios.$get(`https://api.nuxtjs.dev/posts`);
    console.log(posts);
    console.log(context);
    //NOTEIMPORTANT: notice how we don't have to make a variable inside data and set our response data to that variable (which is what I am used to doing with axios and can also be done with fetch, which I haven't learnt about yet). the Nuxt docs explains this well:
    //Unlike fetch, which requires you to set properties on the component instance (or dispatch Vuex actions) to save your async state, asyncData simply merges its return value into your component's local state
    // it seems that the return value is always an object containing our data
    // people really like the ES6 way: return { posts } but I prefer the ES5 classic way
    //NOTEIMPORTANT: this is very important about asyncData: it "cannot access the component instance (this)". we don't have access to our vue instance in async data. instead, "it receives the context as its argument. You can use it to fetch some data and Nuxt.js will automatically merge the returned object with the component data."
    // NOTEIMPORTANT: context, according to the docs: is an object that is "available in specific Nuxt functions like asyncData, plugins, middleware and nuxtServerInit" and "provides additional and often optional information about the current request to the application" . VOICI le argument de notre fonctionne asyncData.
    // initially i wrote it like this: asyncData({ $axios }) with the object containing what I want to use. instead, I will change it to: asyncData(context) and get what I want to use in the meat of the function. more info on context can be found here: "https://nuxtjs.org/docs/2.x/concepts/context-helpers"
    return {
      posts: posts,
    };
  },
};
</script>

<style>
</style>