<template>
  <div class="page__slider trusted-slider">
    <div class="trusted-slider__container _container">
      <div class="trusted-slider__content">
        <div class="trusted-slider__title">TRUSTED BY startups and large enterprises</div>
        <swiper
          :modules="modules"
          :pagination="false"
          :slides-per-view="5"
          :loop="true"
          :breakpoints="{
            '1200': {
              slidesPerView: 5
            },
            '992': {
              slidesPerView: 4
            },
            '768': {
              slidesPerView: 3
            },
            '540': {
              slidesPerView: 2
            },
            '270': {
              slidesPerView: 1
            },
          }"
        >
          <swiper-slide class="trusted-slider__image flex" v-for="item in this.SliderImages" :key="item.name"><img :src="item.image" alt=""></swiper-slide>
        </swiper>
        </div>
    </div>
  </div>
</template>
<script>
// import SwiperClass, { Pagination } from 'Swiper'
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import 'swiper/css'
import 'swiper/css/pagination'
export default {
  data () {
    return {
      SliderImages: [
        {
          name: 'Luminous',
          image: require('@/assets/img/content/Slider_Luminous.png')
        },
        {
          name: 'Sitemark',
          image: require('@/assets/img/content/Slider_Sitemark.png')
        },
        {
          name: 'Pronature',
          image: require('@/assets/img/content/Slider_Pronature.png')
        },
        {
          name: 'Greenish',
          image: require('@/assets/img/content/Slider_Greenish.png')
        },
        {
          name: 'Waveless',
          image: require('@/assets/img/content/Slider_Waveless.png')
        }
      ]
    }
  },
  components: {
    Swiper,
    SwiperSlide
  }
}
</script>
<style lang="scss">
.trusted-slider {
  &__content {
  }
  &__title {
    font-size: 14px;
    line-height: 22px;
    text-align: center;
    text-transform: uppercase;
    color: #FFFFFF;
    margin-bottom: 25px;
  }
  &__image {
    justify-content: center;
    padding: 0 10px;
  }
}
</style>
