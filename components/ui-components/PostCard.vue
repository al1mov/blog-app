<script setup>
const url = process.env.URL;

const { data: posts } = await useFetch(url);

let blogs = ref([]);

blogs = posts;
</script>
<template>
  <article
    class="p-6 rounded-lg border shadow-md bg-gray-800 border-gray-700 hover:border-gray-500"
    v-for="post in blogs"
  >
    <h2
      class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white"
    >
      <nuxt-link :to="{ path: `/posts/${post.id}` }">
        {{ post.title }}
      </nuxt-link>
    </h2>
    <p class="mb-5 font-light text-gray-400">
      {{ new String(post.body).slice(0, 200) }}
    </p>
    <div class="flex justify-between items-center">
      <div class="flex items-center space-x-4">
        <span class="font-medium dark:text-white">
          <span class="text-sm">{{ post.craeted_at }}</span>
        </span>
      </div>
      <nuxt-link :to="{ path: `/posts/${post.id}` }">
        <span
          class="hover:underline text-white items-center flex justify-center"
        >
          Read More
          <i class="fa-solid fa-chevron-right text-xs pl-1"></i>
        </span>
      </nuxt-link>
    </div>
  </article>
</template>
