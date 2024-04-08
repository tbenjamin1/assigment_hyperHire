<template>
    <div class="swiper-container">
        <swiper class="swiper" :options="swiperOption">
            <swiper-slide v-for="index in 6" :key="index">Slide {{ index }}</swiper-slide>
            <div class="swiper-pagination" slot="pagination"></div>
            <div class="swiper-button-prev" slot="button-prev"></div>
            <div class="swiper-button-next" slot="button-next"></div>
        </swiper>
    </div>
</template>

<script>
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'

export default {
    name: 'swiper-example-3d-coverflow',
    components: {
        Swiper,
        SwiperSlide
    },
    data() {
        return {
            swiperOption: {
                effect: 'coverflow',
                grabCursor: true,
                centeredSlides: true,
                slidesPerView: 3,
                // autoplay: {
                //     delay: 3000,
                // },
                coverflowEffect: {
                    rotate: 0,
                    stretch: 80,
                    depth: 200,
                    modifier: 1,
                    slideShadows: false,
                },
                navigation: {
                    nextEl: '.swiper-button-next',
                    prevEl: '.swiper-button-prev',
                }
            }
        }
    },
    methods: {
        isActive(index) {
            // Logic to determine if the current slide is active
            return index === this.$refs.swiper.swiper.realIndex;
        }
    }
}
</script>

<style scoped>
.swiper-container {
   
       width: 750px;
  padding-top: 50px;
  padding-bottom: 50px;
}
.swiper{
    width: 80%;
}
.swiper-slide-active {
  background-color: #FF5733 !important; /* Change the background color of the active slide */
}
.swiper-slide {
    display: flex;
    justify-content: center;
    align-items: center;
   width: 300px !important;
    height: 300px;
    text-align: center;
    font-weight: bold;
    background-color: white;
    border: 1px solid red;
    border-radius: 10px;
    background-position: center;
    background-size: cover;
}
</style>
