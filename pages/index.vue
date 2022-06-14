<template>
  <div>
    <div class="container mx-auto bg-gray-300 p-8">
      <h1 class="font-bold text-gray-600 text-lg">Hello, Tailwind 3!</h1>
    </div>
    <div class="container mx-auto">
      <swiper
      :modules="modules"
      :slides-per-view="3"
      :space-between="50"
      navigation
      :pagination="{ clickable: true }"
      @swiper="onSwiper"
      @slideChange="onSlideChange"
      class="min-h-[300px]"
    >
        <swiper-slide class="grid place-items-center min-h-[300px]">Slide 1</swiper-slide>
        <swiper-slide class="grid place-items-center min-h-[300px]">Slide 2</swiper-slide>
        <swiper-slide class="grid place-items-center min-h-[300px]">Slide 3</swiper-slide>
        <swiper-slide class="grid place-items-center min-h-[300px]">Slide 4</swiper-slide>
        <swiper-slide class="grid place-items-center min-h-[300px]">Slide 5</swiper-slide>
        <swiper-slide class="grid place-items-center min-h-[300px]">Slide 6</swiper-slide>
      </swiper>
    </div>
  </div>
  
</template>
<script lang="ts">
  // import Swiper core and required modules
  import { Navigation, Pagination, Scrollbar, A11y } from 'swiper';

  // Import Swiper Vue.js components
  import { Swiper, SwiperSlide } from 'swiper/vue';

  // Import Swiper styles
  import 'swiper/css';
  import 'swiper/css/navigation';
  import 'swiper/css/pagination';

  // Import Swiper styles
  export default {
    layout: 'default',
    components: {
      Swiper,
      SwiperSlide,
    },
    setup() {
      const onSwiper = (swiper) => {
        console.log(swiper);
      };
      const onSlideChange = () => {
        console.log('slide change');
      };
      return {
        onSwiper,
        onSlideChange,
        modules: [Navigation, Pagination, Scrollbar, A11y],
      };
    },
  };
</script>
