<template>
  <!-- Pilihan Terbaik Untuk Kamu -->
  <section class="relative mt-24 h-[500px] w-full">
    <div class="absolute top-0 left-0 h-full w-1/2 md:w-[30%] bg-gradient-to-b from-shopperly-green-400 to-shopperly-blue rounded-md shadow-md p-5 shadow-inner">
      <h1 class="text-2xl md:text-4xl font-bold text-white w-1/2 md:w-full">Pilihan terbaik untuk kamu!</h1>
      <hr class="text-white my-8 w-2/3 md:w-1/2">
      <p class="text-white text-lg md:text-2xl w-2/3">Jelajahi Produk terbaik sekarang!</p>
    </div>
    <div class="absolute w-[75%] top-1/2 transform -translate-y-1/2 right-0 md:h-2/3">
      <SwiperSlider 
        classSwiper="h-[385px] px-1"
        classSlide="rounded-md "
        withNavigation
        withLoopSlider
        :slideCount="2"
        :breakpoints="{
          768: {
            slidesPerView: 3
          }
        }"
        :data="sliderData"
      >
        <template #body="{ slideData: { title, price, rating, sold }}"> 
          <ProdukCard
            :title="title"
            :price="price"
            :rating="rating"
            :sold="sold"
          />
        </template>
      </SwiperSlider>
    </div>
    
  </section>
</template>

<script>
import { reactive } from "vue";

import SwiperSlider from "../../components/SwiperSlider.vue";
import ProdukCard from "../../components/ProdukCard.vue";

export default {
  components: {
    SwiperSlider,
    ProdukCard
  },
  setup(){
    const sliderData = reactive([
        {
          title: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Explicabo dicta placeat beatae neque laborum labore.',
          price: 1000000,
          rating: 5.0,
          sold: 1000
        },
        {
          title: 'adipisicing elit. Explicabo dicta placeat beatae neque laborum labore.',
          price: 1000000,
          rating: 5.0,
          sold: 1000
        },
        {
          title: 'dolor sit amet consectetur adipisicing elit. icta placeat beatae neque laborum labore.',
          price: 1000000,
          rating: 5.0,
          sold: 1000
        },
        {
          title: 'Explicabo dicta placeat beatae neque laborum labore. Lorem ipsum dolor sit amet consectetur adipisicing elit. ',
          price: 1000000,
          rating: 5.0,
          sold: 1000
        },
        {
          title: 'beatae neque laborum labore Explicabo dicta placeat beatae neque laborum labore.',
          price: 1000000,
          rating: 5.0,
          sold: 1000
        },
      ])
    return {
      sliderData 
    }
  }
}
</script>