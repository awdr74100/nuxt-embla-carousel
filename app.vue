<script setup lang="ts">
import emblaCarouselVue from 'embla-carousel-vue';
import Autoplay from 'embla-carousel-autoplay';

const [emblaRef, emblaApi] = emblaCarouselVue({ align: 'start', loop: true }, [
  Autoplay({ delay: 1000, stopOnInteraction: false }),
]);

onMounted(() => {});
</script>

<template>
  <div class="max-w-screen-xl mx-auto">
    <div class="mx-auto max-w-screen-md">
      <button class="border bg-red-500 px-4 py-3" @click="emblaApi?.reInit()">Re</button>
      <div class="overflow-hidden" ref="emblaRef">
        <div class="flex gap-x-4">
          <template v-for="n in 20" :key="n">
            <div class="last:mr-4 px-5 shrink-0 bg-red-500">AAAAAAAAA {{ n }}</div>
          </template>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.embla {
  overflow: hidden;
}
.embla__container {
  display: flex;
}
.embla__slide {
  flex: 0 0 100%;
  min-width: 0;
}
</style>

<!-- <script setup lang="ts">
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Autoplay } from 'swiper/modules';

import 'swiper/css';
import 'swiper/css/autoplay';
</script>

<template>
  <div class="max-w-screen-xl mx-auto">
    <div class="max-w-screen-md mx-auto">
      <button class="border bg-red-500 px-4 py-3">Re</button>
      <swiper
        :slides-per-view="3"
        :space-between="50"
        :autoplay="{
          delay: 1000,
        }"
        :loop="true"
        :modules="[Autoplay]"
      >
        <template v-for="n in 20" :key="n">
          <swiper-slide>
            <div class="size-52 bg-red-500">Slide {{ n }}</div>
          </swiper-slide>
        </template>
      </swiper>
    </div>
  </div>
</template> -->

<!-- <template>
  <div class="px-5 py-5 max-w-screen-xl mx-auto bg-red-500 text-white">Hello World</div>
</template> -->
