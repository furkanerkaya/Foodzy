<template>
    <div class="rounded-xl shadow-gray-300 shadow-lg text-left relative">
        <button class="p-4 rounded-tr-xl rounded-bl-3xl right-0 max-w-fit absolute bg-[#F53E32]" @click="updateFav()">
            <NuxtImg src="/images/icons/filled-heart.svg" v-if="localFav === 'true'"/>
            <NuxtImg src="/images/icons/heart.svg" v-else />
        </button>
        <div class="px-8 pb-10">
            <div class=" mx-auto items-center flex">
                <NuxtImg :src="image" :alt="title" class="mx-auto my-auto w-64" />
            </div>
            <h3 class=" font-semibold mt-4 ">{{ title }}</h3>
            <p class="text-[#555555] ">{{ description }}</p>
        </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      image: String,
      title: String,
      description: String,
      fav: String
    },
    data() {
      return {
        localFav: this.fav 
      };
    },
    methods: {
      updateFav() {
        if(this.localFav === 'true'){
          this.localFav = 'false'
        }
        else {
          this.localFav = 'true'
        }
        console.log(this.localFav)
      }
    }
  };
  </script>