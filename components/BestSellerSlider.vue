<template>
  <div class="product-slider-container">
    <div class="product-slider-wrapper" :style="wrapperStyle">
      <slot></slot>
    </div>
    <button
      v-if="showControls && currentIndex > 0"
      class="product-slider-control prev w-10 h-10 bg-[#F2F3F4] rounded-full"
      @click="slidePrev"
    >
      <NuxtImg src="/images/icons/left-arrow.svg" class="w-3 h-3 ml-1.5 "/>
    </button>
    
      <button
        v-if="showControls && currentIndex < totalPages - 1"
        class="product-slider-control next w-10 h-10 bg-[#F2F3F4] rounded-full"
        @click="slideNext"
        >
        <NuxtImg src="/images/icons/left-arrow.svg" class="w-3 h-3 rotate-180 ml-1.5"/>
      </button>
    
    <div v-if="showDots" class="product-slider-dots">
      <button
        v-for="(dot, index) in totalPages"
        :key="index"
        :class="{ active: currentIndex === index }"
        @click="goToSlide(index)"
      ></button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    itemsPerPage: {
      type: Number,
      default: 4,
    },
    totalItems: {
      type: Number,
      required: true,
    },
    showControls: {
      type: Boolean,
      default: true,
    },
    showDots: {
      type: Boolean,
      default: false,
    },
    loop: {
      type: Boolean,
      default: false,
    },
    autoplay: {
      type: Boolean,
      default: false,
    },
    autoplayInterval: {
      type: Number,
      default: 3000,
    },
  },
  data() {
    return {
      currentIndex: 0,
      intervalId: null,
    };
  },
  computed: {
    totalPages() {
      return Math.ceil(this.totalItems / this.itemsPerPage);
    },
    wrapperStyle() {
      return {
        transform: `translateX(-${this.currentIndex * (100 / this.totalPages)}%)`,
        width: `${this.totalPages * 100}%`,
      };
    },
  },
  watch: {
    autoplay(newAutoplay) {
      if (newAutoplay) {
        this.startAutoplay();
      } else {
        this.stopAutoplay();
      }
    },
  },
  mounted() {
    if (this.autoplay) {
      this.startAutoplay();
    }
  },
  beforeUnmount() {
    this.stopAutoplay();
  },
  methods: {
    slideNext() {
      if (this.loop) {
        this.currentIndex = (this.currentIndex + 1) % this.totalPages;
      } else if (this.currentIndex < this.totalPages - 1) {
        this.currentIndex++;
      }
    },
    slidePrev() {
      if (this.loop) {
        this.currentIndex = (this.currentIndex - 1 + this.totalPages) % this.totalPages;
      } else if (this.currentIndex > 0) {
        this.currentIndex--;
      }
    },
    goToSlide(index) {
      this.currentIndex = index;
    },
    startAutoplay() {
      this.intervalId = setInterval(this.slideNext, this.autoplayInterval);
    },
    stopAutoplay() {
      clearInterval(this.intervalId);
      this.intervalId = null;
    },
  },
};
</script>

<style scoped>
.product-slider-container {
  position: relative;
  overflow: hidden;
}

.product-slider-wrapper {
  display: flex;
  transition: transform 0.3s ease-in-out;
}

.product-slider-wrapper > * {
  flex: 0 0 calc(100% / var(--items-per-page)); /* Dinamik genişlik */
  margin-right: 16px; /* İsteğe bağlı boşluk */
}

.product-slider-wrapper > *:last-child {
  margin-right: 0;
}

.product-slider-control {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  
  cursor: pointer;
  padding: 8px;
  z-index: 10;
}

.product-slider-control.prev {
  left: 10px;
}

.product-slider-control.next {
  right: 10px;
}

.product-slider-dots {
  text-align: center;
  margin-top: 10px;
}

.product-slider-dots button {
  background-color: #ddd;
  border: none;
  border-radius: 50%;
  width: 10px;
  height: 10px;
  margin: 0 5px;
  padding: 0;
  cursor: pointer;
}

.product-slider-dots button.active {
  background-color: #333;
}
</style>