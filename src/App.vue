<script setup>
// import Vue2Search from "./components/Vue2Search.vue";
import BlogPostList from "./components/BlogPostList.vue"
</script>

<template>
  <div>
    <!-- <Vue2Search /> -->
    <BlogPostList />
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
