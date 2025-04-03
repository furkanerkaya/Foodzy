<template>
    <div class="rounded-2xl border-[1px]">
      <div :class="color" style="max-inline-size: fit-content" class="px-3 rounded-tl-2xl rounded-br-2xl text-white">
        {{ tagText }}
      </div>
      <div class="px-8 pt-4 items-center flex text-center">
        <NuxtImg :src="image" :alt="title" class="mx-auto my-auto w-24" />
      </div>
      <p class="font-semibold text-[#ADADAD] text-xs text-left px-4">{{ title }}</p>
      <p class="text-[#253D4E] text-[16px] text-left px-4 font-bold">{{ description }}</p>
      <StarRating 
        :initialRating="rating" 
        :totalStars="5" 
        @update:rating="updateRating" 
        class="text-left px-4"
      />
      <div class="flex px-4">
        <p class="font-bold text-[#3BB77E] text-lg">${{ newPrice }}</p>
        <p class="font-medium text-[#ADADAD] text-xs mt-[6px] ml-4 line-through">${{ oldPrice }}</p>
      </div>
      <div class="bg-[#E9ECEF] rounded-full h-1 mx-4">
        <div class="bg-[#F53E32] h-1 rounded-full" :style="ratio"></div>
      </div>
      <div class="text-left px-4 text-xs mt-2 font-normal">
        Sold: {{ sold }} / {{ stock }}
      </div>
      <div class="mt-2 px-4 mb-2">
        <button class="w-full py-2 text-white bg-[#F53E32] rounded-lg">Add To Cart</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      color: String,
      tagText: String,
      image: String,
      title: String,
      description: String,
      newPrice: Number,
      oldPrice: Number,
      sold: Number,
      stock: Number,
      rating: Number,
    },
    computed: {
      ratio() {
        return `width: ${(this.sold * 100) / this.stock}%`;
      }
    },
    methods: {
      updateRating(newRating) {
        this.rating = newRating;
      }
    }
  };
  </script>
  
  <style>

  </style>
  