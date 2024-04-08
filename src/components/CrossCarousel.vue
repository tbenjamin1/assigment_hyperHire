<template>
    <div class="swiper-container">
        <swiper class="swiper-carousel" :options="swiperOption">
            <swiper-slide v-for="index in 3" :key="index">
                <div class="container">
                    <!-- <q-avatar round size="50px"><img src="https://cdn.quasar.dev/img/avatar.png" class="q-my-sm" alt=""></q-avatar> -->
                    <q-item clickable v-ripple>
                        <q-item-section side>
                            <q-avatar round size="80px">
                                <img src="https://cdn.quasar.dev/img/avatar.png" />
                                <!-- <q-badge floating  icon="signal_wifi_off" color="teal"></q-badge> -->
                                <q-badge floating color="teal">
                                    <q-icon name="flag" />
                                </q-badge>
                            </q-avatar>
                        </q-item-section>
                    </q-item>
                    <div class="title q-px-sm titles">
                        <span>Abhishek Gupta</span>
                        <span class="text-blue sub-title">마케팅 · <strong>2y+</strong></span>
                    </div>
                    <div>
                        <div>
                            <div class="footer-slide-top">
                                <span>마케팅 콘텐츠 제작</span>
                                <span class="q-my-sm">인스타그램 관리</span>
                            </div>
                        </div>
                        <div class="footer-slider ">
                            <span>트위터 관리</span>
                            <span>인스타그램 관리</span>
                        </div>
                    </div>
                </div>
            </swiper-slide>
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

    width: 100%;
}

.titles {
    display: flex;
    flex-direction: column;
}

.swiper-carousel {
    width: 80%;
}

.swiper-carousel .swiper-slide-active {
    background-color: white !important;
    /* Change the background color of the active slide */
}

.swiper-carousel .swiper-slide {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 200px !important;
    height: 300px;
    text-align: center;
    font-weight: bold;
    background-color: #EDFCFF;

    border-radius: 10px;
    background-position: center;
    background-size: cover;
}

.swiper-carousel .swiper-button-prev:after,
.swiper-carousel .swiper-button-next:after {
    font-size: 20px;
    font-weight: bolder;
    position: absolute;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
}

.container {
    display: flex;
    align-content: center;
    flex-direction: column;
}

.rounded-img {
    object-fit: cover;
    width: 100%;
    height: 100%;
    border-radius: 10px;

}

.q-badge--floating {
    position: absolute;
    top: 57px;
    right: -3px;
    cursor: inherit;
}

.sub-title {
    font-size: 10px;
}

.footer-slider {
    display: flex;
    font-size: 10px;
    color: #c1c5cf;

}

.footer-slide-top {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    font-size: 10px;
    color: #c1c5cf;
}

.footer-slide-top span {

    color: #c1c5cf;
    border: 1px solid #c1c5cf;
    width: 70%;
    border-radius: 5px;
}

.footer-slider span {
    color: #c1c5cf;
    border: 1px solid #c1c5cf;
    border-radius: 5px;
    padding: 2px 5px;
    margin: 0px 2px;
}
@media (max-width: 500px) {
 
   .swiper-carousel {
    width: 100%;
   }
   .swiper-carousel .swiper-slide {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 166px !important;
    height: 300px;
    text-align: center;
    font-weight: bold;
    background-color: #EDFCFF;

    border-radius: 10px;
    background-position: center;
    background-size: cover;
}
.swiper-wrapper {
    left: -16% !important;
}
}
</style>
