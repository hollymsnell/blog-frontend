<template>
  <div class="home">
    <h1>{{ post.title }}</h1>
    <img v-bind:src="post.image" v-bind:alt="post.title" style="max-width: 250px" />
    <p>{{ post.body }}</p>
    <div>
      <router-link to="/posts">Back to all posts</router-link>
      <p>
        <button v-on:click="destroyPost()">Delete Post</button>
      </p>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      post: {},
    };
  },
  created: function () {
    axios.get(`/posts/${this.$route.params.id}`).then((response) => {
      this.post = response.data;
    });
  },
  methods: {
    destroyPost() {
      axios.delete(`/posts/${this.post.id}`).then((response) => {
        console.log(response);
        this.$router.push("/posts");
      });
    },
  },
};
</script>
