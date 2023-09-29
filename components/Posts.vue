<script setup>
const url = "https://blog-api-oab6.onrender.com/posts";
const { data: posts } = await useFetch(url);
let blogs = ref([]);
blogs = posts;
console.log(blogs);
</script>
<template>
  <section>
    <div class="py-8 px-4 bg-black mx-auto max-w-screen-xl lg:py-16 lg:px-6">
      <div class="mx-auto max-w-screen-sm text-center lg:mb-16 mb-8">
        <h2
          class="mb-4 text-3xl lg:text-4xl tracking-tight font-extrabold text-white"
        >
          Our Blog
        </h2>
        <p class="font-light sm:text-xl text-gray-400">
          We use an agile approach to test assumptions and connect with the
          needs of your audience early and often.
        </p>
      </div>
      <div class="grid gap-8 lg:grid-cols-2">
        <article
          class="p-6 rounded-lg border shadow-md bg-gray-800 border-gray-700 hover:border-gray-500"
          v-for="post in blogs"
        >
          <h2
            class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white"
          >
            <a href="">
              {{ post.title }}
            </a>
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
            <a href="">
              <span
                class="hover:underline text-white items-center flex justify-center"
              >
                Read More
                <i class="fa-solid fa-chevron-right text-xs pl-1"></i>
              </span>
            </a>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>
