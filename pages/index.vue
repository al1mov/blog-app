<script setup>
import Navbar from "../components/Navbar.vue";
import Posts from "../components/Posts.vue";

useSeoMeta({
  title: "Blog",
  ogTitle: "Blog",
  description: "Blog site using nuxt.js 3",
  ogDescription: "Blog site using nuxt.js 3",
  ogImage:
    "https://images.unsplash.com/photo-1471107340929-a87cd0f5b5f3?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1373&q=80",
  twitterCard: "summary_large_image",
});
</script>
<template>
  <NuxtLoadingIndicator />
  <Navbar class="h-[50px] sticky" />
  <Posts />
  <NuxtPage />
</template>
