<template>
  <div class="posts-index">
    <div v-for="post in posts" v-bind:key="post.id">
      <h2> <u> {{ post.title }} </u> </h2>
      <img v-bind:src="post.image" alt="" />
      <p>{{ post.body }} </p>
    </div>
  </div>
</template>

<style></style>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      posts: [],
    };
  },
  created: function () {
    axios.get("/api/posts").then((response) => {
      console.log(response.data);
      this.posts = response.data;
    });
  },
  methods: {},
};
</script>