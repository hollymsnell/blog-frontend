<template>
  <div class="home">
    <img
      alt="Vue logo"
      src="https://www.jimdo.com/static/7f58e83e14a16db25da8e56995f710b8/ba332/hero.webp"
      style="max-width: 400px"
    />
    <HelloWorld msg="Time to Write Some Blogs" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "HomeView",
  components: {
    HelloWorld,
  },
};
</script>
