<script setup>
import Post from "@/components/ui-components/PostCard.vue";
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
        <Post />
      </div>
    </div>
  </section>
</template>
