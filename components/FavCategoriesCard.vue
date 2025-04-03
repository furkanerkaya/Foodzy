<template>
    <div class="rounded-lg shadow-lg py-6 px-8">
      <div class="rounded-full bg-[#C0B2632B] w-32 h-32 items-center flex mx-auto">
        <NuxtImg :src="image" :alt="title" class="mx-auto my-auto w-20" />
      </div>
      <h3 class=" font-semibold">{{ title }}</h3>
      <p class="text-[#555555]">({{ description }})</p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      image: String,
      title: String,
      description: String,
    },
  };
  </script>