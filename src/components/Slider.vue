<template lang="">
       
         <div class="flex  w-4/5 mx-auto">
            <div class="flex w-full justify-between items-center">
                <swiper
                class="flex"
                :modules="modules"
                :loop="true"
                :pagination="{clickable: true}"
                :autoplay="{
                    delay: 7000,
                    disableOnInteraction: false,
                    pauseOnMouseEnter: true
                }"
                >
                    <swiper-slide v-for="text in swiperTextBase" :key="text.title">
                    <div class="rev_slider w-[400px] h-60 border border-3 border-red-500 rounded-2xl mr-2">
                        <div class="slide">
                            <div class="avatar w-[400px] flex justify-between items-center p-2 ">
                                <img :src="text.img" alt="image">
                            <div class="name">
                                <h1 class="font-medium text-xl">{{text.userName}}</h1> 
                                <p class="text-lg">{{text.country}}</p>
                            </div>
                            <div class="flex m-1">
                                4.5 
                                <img class="m-1" src="./assets/star.png" alt="">
                                </div>
                            </div>
                            <div class="w-[390px] p-6">
                                <p>{{text.title}}</p>
                            </div>
                        </div>
                    </div>
                    </swiper-slide>
                </swiper>        
            </div>
         </div>
         <div class="flex w-4/5 mx-auto justify-between pt-3 items-center pb-10">
             <div>
                    <button class="w-12 h-3.5 bg-red-500 border rounded-xl"></button>
                    <button class="w-3.5 h-3.5 bg-red-500 border rounded-xl"></button>
                    <button class="w-3.5 h-3.5 bg-red-500 border rounded-xl"></button>
                    <button class="w-3.5 h-3.5 bg-red-500 border rounded-xl"></button>
            </div>
                <div class="flex items-center">
                    <button @click="leftSlide()" class="w-20"><img class="w-13" src="./assets/prevbtn.png" alt=""></button>
                    <button @click="rightSlide()" class="w-20"><img class="w-13" src="./assets/nextbtn.png" alt=""></button>
            </div>
        </div>
</template>
<script>

    
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Autoplay, Pagination } from 'swiper'
// import 'swiper/css';
// import 'swiper/css/paginatiom';
import { ref } from 'vue';
export default {
    component: {
        Swiper,
        SwiperSlide
    },
    setup() {
        const swiperTextBase = ref([
            {
                userName: 'Viezh Robert',
                country: 'Warsaw, Poland',
                title: '“Wow... I am very happy to use this VPN, it turned out to be more than my expectations and so far there have been no problems. LaslesVPN always the best”.',
                // img: require('../assets/user1.png')
            },
            {
                userName: 'Yessica Christy',
                country: 'Shanxi, China',
                title: '“I like it because I like to travel far and still can connect with high speed.”.',
                // img: require('../assets/user2.png'),
            },
            {
                userName: 'Kim Young Jou',
                country: 'Seoul, South Korea',
                title: '“This is very unusual for my business that currently requires a virtual private network that has high security.”.',
                // img: require('../assets/user3.png'),
            }
        ]);
        return { modules: [Autoplay, Pagination], swiperTextBase }
    }
}
</script>
<style lang="">
    
</style>