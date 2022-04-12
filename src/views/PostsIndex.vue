<template>
  <div class="home">
    <h1>{{ message }} count: {{ posts.length }}</h1>
    <div v-for="post in posts" v-bind:key="post.id">
      <h3>{{ post.title }}</h3>
      <p>{{ post.body }}</p>
      <img v-bind:src="post.image" v-bind:alt="post.title" style="max-width: 250px" />
      <div>
        <router-link v-bind:to="`/posts/${post.id}`">Show More</router-link>
        |
        <router-link v-bind:to="`/posts/${post.id}/edit`">Edit</router-link>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      message: "My Posts",
      posts: [],
    };
  },
  created: function () {
    this.indexPosts();
  },
  methods: {
    indexPosts() {
      axios.get("/posts").then((response) => {
        console.log(response.data);
        this.posts = response.data;
      });
    },
  },
};
</script>

<style></style>
