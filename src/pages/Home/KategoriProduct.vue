<template>
  <!-- Kategori Product -->
  <section class="h-[400px] grid grid-cols-5 grid-rows-3 gap-3 mt-10">
    <div class="col-span-3 row-span-2 bg-shopperly-green-100 grid place-items-center">Event or Promo Product</div>
    <div class="col-span-1 row-span-2 bg-shopperly-green-100 grid place-items-center">Top Product</div>
    <div class="col-span-1 row-span-2 bg-shopperly-green-100 grid place-items-center">Related Product</div>
    <div class="category relative overflow-hidden col-span-5 row-span-1 bg-shopperly-green-100 grid place-items-center">
      <SwiperSlider 
        classSwiper="w-full px-2"
        classSlide="rounded-md !w-auto"
        slideCount="auto"
        :spaceBetween="15"
        :data="categories"
      >
        <template #body="{ slideData: { icon, name }}"> 
          <div class="border-2 border-shopperly-green-400 rounded-2xl flex items-center px-2.5 py-1.5 cursor-pointer">
          <div class="bg-shopperly-green-400 rounded-full p-3">
            <!-- svg -->
            {{ icon }}
          </div>
          <h3 class="pl-2 text-sm">{{ name }}</h3>
        </div>
        </template>
      </SwiperSlider>
    </div>
  </section>
</template>

<script>
import { reactive } from 'vue'

import SwiperSlider from "../../components/SwiperSlider.vue";

export default {
  components: {
    SwiperSlider
  },
  setup(){
    const categories = reactive([
      {
        icon: '',
        name: 'Fashion'
      },
      {
        icon: '',
        name: 'Health'
      },
      {
        icon: '',
        name: 'Technology'
      },
      {
        icon: '',
        name: 'Electronic'
      },
      {
        icon: '',
        name: 'Handphone'
      },
      {
        icon: '',
        name: 'Fashion'
      },
      {
        icon: '',
        name: 'Health'
      },
      {
        icon: '',
        name: 'Technology'
      },
      {
        icon: '',
        name: 'Electronic'
      },
      {
        icon: '',
        name: 'Handphone'
      },
    ])

    return {
      categories
    }
  }
}
</script>

<style lang="postcss">
.category:before {
  content: '';
  box-shadow: 0 0 20px 10px rgba(0, 0, 0, 0.05);
  z-index: 1;
  @apply absolute top-0 -left-5 w-5 h-full
}
.category:after {
  content: '';
  box-shadow: 0 0 20px 10px rgba(0, 0, 0, 0.05);
  z-index: 1;
  @apply absolute top-0 -right-5 w-5 h-full
}
</style>
