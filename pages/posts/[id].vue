<script setup>
const route = useRoute();
const id = route.params.id;
const url = "https://blog-api-oab6.onrender.com/posts/" + id;
const { data: post } = await useFetch(url);
let blog = reactive([]);
blog = post;
console.log(post);
</script>
<template>
  <Head>
    <Title>{{ blog.title }}</Title>
    <Meta name="description" :content="new String(blog.body).slice(0, 200)" />
    <Meta name="robots" content="INDEX, FOLLOW" />
    <Meta name="og:title" :content="blog.title" />
    <Meta name="og:image" :content="blog.image" />
    <Meta name="og:type" content="website" />
    <Meta name="twitter:image" :content="blog.image" />
  </Head>
  <div class="w-full min-h-screen max-h-max bg-black pb-[30px]">
    <div
      class="w-[95%] flex justify-start text-white text-2xl items-center p-[20px] m-auto lg:w-[70%]"
    >
      <nuxt-link to="/">
        <Icon name="uil:arrow-left" class="pr-[5px] text-4xl" />
        Navigate to back
      </nuxt-link>
    </div>
    <div
      class="w-[95%] m-auto text-white items-center text-center pt-[20px] font-bold text-4xl lg:w-[70%]"
    >
      {{ blog.title }}
    </div>
    <div
      class="w-[95%] h-[10%] m-auto items-center flex justify-center pt-[20px] lg:w-[70%] lg:h-[5%]"
    >
      <NuxtImg
        class="w-full h-full rounded-lg"
        :src="blog.image"
        format="webp"
        fit="cover"
        loading="lazy"
      />
    </div>
    <div
      class="w-[95%] m-auto text-left text-gray-500 text-md pt-[15px] lg:w-[70%]"
    >
      {{ blog.craeted_at }}
    </div>
    <div class="w-[95%] m-auto text-white pt-[30px] lg:w-[70%]">
      {{ blog.body }}
    </div>
  </div>
</template>
