<script setup>
import Navbar from "../components/Navbar.vue";
import Posts from "../components/Posts.vue";

useSeoMeta({
  title: "Blog",
  ogTitle: "Blog",
  description: "Blog site using nuxt.js 3",
  ogDescription: "Blog site using nuxt.js 3",
  ogImage:
    "https://images.lumacdn.com/cdn-cgi/image/format=auto,fit=cover,dpr=1,quality=75,width=960,height=480/event-covers/50/653c8dc8-2871-4cc0-b768-9b634df65b5a",
  twitterCard: "summary_large_image",
});
</script>
<template>
  <Navbar class="h-[50px] sticky" />
  <Posts />
  <NuxtPage />
</template>
