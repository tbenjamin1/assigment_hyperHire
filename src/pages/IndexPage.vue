<template>
  <q-page class="q-px-xl">
    <div class="row main-container">
      <div class="fade-in-delay left-container" style="">
        <q-chat-message class="left-message" sent >
      <div :class="{ 'bg-color-small-screen': $q.screen.lt.sm }" class="left_message">풀타임, 파트타임</div>
  </q-chat-message>

        <div class="q-pb-md column-container" color="white">
          <div class="main-title q-py-sm fade-in-up">최고의 실력을 가진 <br>
            외국인 인재를 찾고 계신가요?</div>

          <div class="sub-title fade-in-up">
            법률 및 인사관리 부담없이 <br>
            1주일 이내에 원격으로 채용해보세요
          </div>

          <div v-if="$q.screen.gt.xs" class="content q-py-sm">
            개발자가 필요하신가요?
          </div>
          <div class="row q-my-lg fade-in " v-if="$q.screen.gt.xs">
            <div class="sub-content q-py-sm fade-in-one">
              <span>평균 월 120만원</span>
              <div>
                임금을 해당 국가를 <br> 기준으로 계산합니다
              </div>
            </div>
            <div class="q-mx-lg  q-py-sm sub-content fade-in-one ">
              <span>최대 3회 인력교체</span>
              <div>
                막상 채용해보니 맞지 <br> 않아도 걱정하지 마세요
              </div>
            </div>
            <div class="sub-content q-py-sm fade-in-one">
              <span>평균 3일, 최대 10일</span>
              <div>
                급하게 사람이 필요한 <br> 경우에도 빠른 채용이 <br> 가능합니다
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="fade-in-delay right-container">
        <div style="">
          <q-chat-message class="right-message q-mb-lg" sent>
            <div class="row items-center">
              <img src="/icons/usd.png" alt="Image" class="ussd-icon">
              <span class="right_message">월 <strong>100</strong> 만원</span>
            </div>
          </q-chat-message>
          <div class="q-mx-lg">
            <Carousel />
          </div>
        </div>
      </div>

    </div>

    <div class="row main-container q-my-sm fade-in-animation ">
      <div class="q-my-lg" v-if="$q.screen.lt.sm">
        <div class="row" >
          <div class="checked-box" > <img src="/icons/Checkbox.png" alt="Image" class="checked-icon"> 한국어 능력 </div>
          <div class="checked-box" >
            <img src="/icons/Checkbox.png" alt="Image" class="checked-icon"> 업무 수행 능력
          </div>
        </div>
        <div class="row q-my-sm" >
            <div class="checked-box" > <img src="/icons/Checkbox.png" alt="Image" class="checked-icon"> 한국어 능력 </div>
            <div class="checked-box" >
              <img src="/icons/Checkbox.png" alt="Image" class="checked-icon"> 업무 수행 능력
            </div>
          </div>
        <div class="quick-link-check q-py-sm">
          개발자가 필요하신가요?
        </div>
      </div>
      <CardSlider :sliderItems="sliderItems" v-if="$q.screen.gt.xs" />

    </div>
  </q-page>
</template>

<script>
import { ref } from "vue";
import CardSlider from "../components/CardSlider.vue";
import Carousel from "../components/CrossCarousel.vue";

export default {
  components: {
    CardSlider,
    Carousel,
  },
  data() {
    return {

      sliderItems: [
        { src: "/icons/personview.png", title: " 해외 개발자 원격 채용" },
        { src: "/icons/image-icon.png", title: "외국인 원격 채용 (비개발)" },
        { src: "/icons/circle.png", title: "한국어 가능 외국인 채용" },
        { src: "/icons/cube.png", title: "해외 개발자 활용 서비스" },
        // Add more items as needed
      ],
    };
  },
};
</script>
<style>
.main-container {
  display: flex;
  justify-content: flex-start;
  margin-left: 155px;
}



.left-container {
  width: 40%;
}

.right-container {
  width: 60%;
}

.q-message-container {
  display: flex;
  justify-content: center;
  align-items: center;
}

/* FadeIn after title and subtitle shown(delay 300ms) */
.fade-in-delay {
  animation: fadeIn 0.3s 300ms forwards;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}

/* FadeInUp(500ms) */
.fade-in-up {
  animation-name: fadeInUp;
  animation-duration: 500ms;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* fadeIn(500ms)*/
.fade-in-animation {
  animation-name: fade-in;
  animation-duration: 500ms;
}

@keyframes fade-in {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}

/* fade-in-one-animation */
.fade-in-one {
  opacity: 0;
  animation: fade-in-one-animation 500ms ease-in-out forwards;
}

@keyframes fade-in-one-animation {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}

.column-container {
  color: white;
}

.left-message .q-message-text--sent:last-child:before {
  left: 13%;
  /* Change from right to left */
  bottom: -6.5px;
  transform: translateX(-50%) rotate(170deg);
  border-top: 0 solid transparent;
  border-bottom: 8px solid currentColor;
  border-left: 8px solid transparent;
  border-right: 8px solid transparent;
  display: flex;
  justify-content: center;
  align-items: center;
}

.right-message .q-message-text--sent:last-child:before {
  left: 50%;
  /* Change from right to left */
  bottom: -6.5px;
  transform: translateX(-50%) rotate(170deg);
  border-top: 0 solid transparent;
  border-bottom: 8px solid currentColor;
  border-left: 8px solid transparent;
  border-right: 8px solid transparent;
}

.right_message {
  color: #00c696;
}

.right-message .q-message-text:last-child {
  min-height: unset;
}

.left-message .q-message-text:last-child {
  min-height: unset;
  padding: 8px 10px;
}

.q-message-text {
  padding: 2px 10px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.q-message-text--sent {
  color: white;
}

.left_message {
  display: flex;
  justify-content: center;
  align-items: center;
  color: #40e2e8;
}

.main-title {
  font-weight: 600;
  font-size: 26px;
}

.sub-title {
  font-weight: 600;
  font-size: 20px;
}

.content {
  font-weight: 500;
  font-size: 14px;
  text-decoration: underline;
}

.sub-content {
  border-top: 1px solid white;
}

.q-px-xl {
  padding-left: unset;
  padding-right: unset;
  min-height: unset !important;
}
.checked-box{
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
}
.checked-icon{
  margin: 0px 10px;
}
.quick-link-check{
  margin: 0px 10px;
  text-decoration: underline;
  color: #FBFF23;
}
@media (max-width: 600px) {
  .left_message .q-message-container {
    display: flex;
    justify-content: flex-end !important;
    align-items: center;
  }

  .left_message {
    display: flex;
    justify-content: flex-end !important;
    align-items: center;
    color: white;
  }
.left-message .q-message-text:last-child {
background-color: #8BC4FF;
color: white;
}
  .main-container {
    margin-left: unset;
    display: flex;
    flex-direction: column;
  }

  .left-container {
    width: 100%;
  }

  .right-container {
    width: 100%;
  }
  .main-title {
  font-weight: 600;
  font-size: 25px;
   padding: 0px 20px;
}

.sub-title {
  font-weight: 600;
  font-size: 16px;
  padding: 10px 20px;
}
}

@media (max-width: 320px) {
  .main-container {
    margin-left: unset;
  }
}
</style>
