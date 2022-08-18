<template>
  <div class="flex w-[1200px] mx-auto pt-10 pb-8">
    <swiper :modules="modules" :slides-per-view="3" :space-between="50" navigation :pagination="{ clickable: true }"
      :scrollbar="{ draggable: true }" @swiper="onSwiper" @slideChange="onSlideChange">
      <swiper-slide v-for="slider in sliders" :key="slider.id" class="pb-10">
        <div class="rev_slider w-[400px] h-60 border border-3 border-red-500 rounded-2xl mr-2">
          <div class="slide">
            <div class="avatar w-[400px] flex justify-between items-center p-2 ">
              <img :src="slider.img" alt="image">
              <div class="name">
                <h1 class="font-medium text-xl">{{ slider.userName }}</h1>
                <p class="text-lg">{{ slider.country }}</p>
              </div>
              <div class="flex m-1">
                4.5
                <img class="m-1" src="@/assets/star.png" alt="">
              </div>
            </div>
            <div class="w-[390px] p-6">
              <p>{{ slider.title }}</p>
            </div>
          </div>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>
<script>
// import Swiper core and required modules
import { Navigation, Pagination, Scrollbar, A11y } from 'swiper';

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';

// Import Swiper styles
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';
import 'swiper/css/scrollbar';

// Import Swiper styles
export default {
  name: "SliderSwiper",
  data() {
    return {
      sliders: [
        {
          userName: 'Viezh Robert',
          country: 'Warsaw, Poland',
          title: '“Wow... I am very happy to use this VPN, it turned out to be more than my expectations and so far there have been no problems. LaslesVPN always the best”.',
          img: require('@/assets/user1.png')
        },
        {
          userName: 'Yessica Christy',
          country: 'Shanxi, China',
          title: '“I like it because I like to travel far and still can connect with high speed.”.',
          img: require('@/assets/user2.png'),
        },
        {
          userName: 'Kim Young Jou',
          country: 'Seoul, South Korea',
          title: '“This is very unusual for my business that currently requires a virtual private network that has high security.”.',
          img: require('@/assets/user3.png'),
        },
        {
          userName: 'Viezh Robert',
          country: 'Warsaw, Poland',
          title: '“Wow... I am very happy to use this VPN, it turned out to be more than my expectations and so far there have been no problems. LaslesVPN always the best”.',
          img: require('@/assets/user1.png')
        },
        {
          userName: 'Yessica Christy',
          country: 'Shanxi, China',
          title: '“I like it because I like to travel far and still can connect with high speed.”.',
          img: require('@/assets/user2.png'),
        },
        {
          userName: 'Kim Young Jou',
          country: 'Seoul, South Korea',
          title: '“This is very unusual for my business that currently requires a virtual private network that has high security.”.',
          img: require('@/assets/user3.png'),
        }
      ]
    }
  },
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