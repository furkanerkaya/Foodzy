<template>
    <div class="rounded-xl text-left relative">
        <div class="z-10">
            <NuxtImg :src="image" class="sm:w-80 w-full mt-2 rounded-xl"/>
        </div>
        <div class="px-4 -mt-10">
            <div class="py-6  font-bold text-sm text-[#253D4E] bg-white z-50 rounded-xl shadow-lg relative">
                <div class="px-4">{{ title }}</div>
                <div class="text-[#B6B6B6]">
                    <StarRating 
                        :initialRating="score" 
                        :totalStars="5" 
                        @update:rating="updateRating" 
                        class="text-left px-4"
                    />
                </div>
                <div class="text-xs font-normal flex px-4">
                    <div class="text-[#B6B6B6]">By</div>
                    <div class="text-[#3BB77E] ml-1">{{ owner }}</div>
                </div>
                <div class="flex justify-between px-4">
                    <div class="flex">
                        <div class="font-bold text-[#3BB77E] text-lg">${{ newPrice }}</div>
                        <div class="font-medium text-[#ADADAD] text-xs mt-[6px] ml-2 line-through">${{ oldPrice }}</div>
                    </div>
                    <div>
                        <button class="bg-[#F53E32] flex rounded-md px-4 py-2">
                            <NuxtImg src="/images/icons/shopping-cart.svg" class="w-3"/>
                            <p class="text-white ml-1">Add</p>
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
        image: String,
        title: String,
        score: String,
        owner: String,
        newPrice: String,
        oldPrice: String
    },
    methods: {
      updateRating(newRating) {
        this.score = newRating;
      }
    }
  };
  </script>