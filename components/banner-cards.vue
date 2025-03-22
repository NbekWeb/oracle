<template>
  <client-only>
    <swiper
      :slides-per-view="'auto'"
      :space-between="10"
      :loop="true"
      :autoplay="{
        delay: 3000,
        disableOnInteraction: false,
      }"
    >
      <swiper-slide v-for="(card, i) in cards" :key="i">
        <img :src="card" />
      </swiper-slide>
    </swiper>
  </client-only>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator'
import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/swiper-bundle.css'

import card1 from '@/assets/svg/card1.svg'
import card2 from '@/assets/svg/card2.svg'
import card3 from '@/assets/svg/card3.svg'
import card4 from '@/assets/svg/card4.svg'

@Component({
  components: {
    Swiper,
    SwiperSlide,
  },
})
export default class BannerCards extends Vue {
  cards = [card1, card2, card3, card4]
}
</script>

<style scoped lang="scss">
.swiper {
  width: 100%;
  height: 158px;
}
.swiper-slide {
  width: auto;
  display: flex;
  justify-content: center;
  align-items: center;
}
.swiper-slide img {
  width: 133px;
}
</style>

<!-- <style scoped lang="scss">
.banner-cards {
  display: flex;
  height: 158px;
  width: 100%;
  overflow-x: auto;
  gap: 10px;
  img {
    width: 133px;
  }
}
</style> -->
