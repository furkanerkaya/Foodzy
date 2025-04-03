<template>
    <div class="star-rating mr-auto">
      <span 
        v-for="index in totalStars" 
        :key="index"
        class="text-md text-gray-300 cursor-pointer"
        :class="{'text-yellow-400': index <= rating}"
        @click="setRating(index)"
      >
        ★
      </span>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      initialRating: {
        type: Number,
        default: 0,
      },
      totalStars: {
        type: Number,
        default: 5,
      },
    },
    data() {
      return {
        rating: this.initialRating,
      };
    },
    methods: {
      setRating(index) {
        this.rating = index;
        this.$emit('update:rating', this.rating);
      },
    },
  };
  </script>
