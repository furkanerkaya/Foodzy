<template>
    <div class="rounded-lg bg-[#F4F6FA] py-2 px-2 sm:w-1/5 justify-center sm:justify-start flex items-center mt-2">
        <div class="max-w-fit max-h-fit p-2">
            <NuxtImg :src="image" :alt="title" class="mx-auto my-auto w-12" />
        </div>
        <div class="ml-1 ">
          <h3 class=" font-semibold text-sm text-[#242424]">{{ title }}</h3>
          <p class="text-[#ADADAD] font-medium text-xs">({{ description }})</p>
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