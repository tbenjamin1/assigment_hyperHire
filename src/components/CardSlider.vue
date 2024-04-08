
<template>
    <swiper class="swiper_slider" :options="swiperOption">
         <swiper-slide v-for="(item, index) in sliderItems" :key="index">
                <div class="main-slider">
                    <q-avatar rounded size="50px"><img :src="item.src"></q-avatar>
                    <span class="title q-px-sm">{{ item.title }}</span>
                </div>
            </swiper-slide>
    </swiper>
</template>

<script>
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'

export default {
    props: {
        sliderItems: {
            type: Array
        }
    },
    components: {
        Swiper,
        SwiperSlide
    },
    
    data() {
        return {
            swiperOption: {
                slidesPerView: 3,
                spaceBetween: 30,
                autoplay: {
                    delay: 3000,
                },
                pagination: {
                    el: '.swiper-pagination',
                    clickable: true
                }
            }
        }
    }
}
</script>

<style  scoped>
.swiper_slider .swiper-slide {
    display: flex;
    align-items: center;
    margin-right: 10px !important;
    width: 300px !important;
    padding: 0px 10px;
    height: 80px;
    box-shadow: 0 15px 25px rgba(129, 124, 124, 0.2);
    border-radius: 5px;
    backdrop-filter: blur(14px);
    background-color: rgba(255, 255, 255, 0.2);
}
.main-slider {
    display: flex;
    justify-content: flex-start;
    align-items: center;

}

.title {
    font-size: 12px;
    font-weight: bolder;
    color: white;
} 
</style>