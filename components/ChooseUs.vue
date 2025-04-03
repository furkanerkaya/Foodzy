<template>
    <div class="rounded-lg shadow-lg py-6 px-8 flex items-center">
        <div class="rounded-full shadow-lg max-w-fit max-h-fit p-4 mt-10 sm:mt-0">
            <NuxtImg :src="image" :alt="title" class="mx-auto my-auto w-12" />
        </div>
        <div class="sm:ml-4">
          <h3 class=" font-semibold text-3xl">{{ title }}</h3>
          <p class="text-gray-500 font-medium text-sm">({{ description }})</p>
        </div>
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