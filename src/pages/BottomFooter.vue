<template>
    <div class="footer-container ">
        <div class="footer-left">
            <div class="row items-center">
                <img src="/icons/footer_icon.png" alt="Image" class="logo-icon">
                <span class="q-px-sm text-weight-bold text-black">hyperhire</span>
            </div>
            <div class="q-py-sm">
                우리는 국가의 장벽을 넘어 최고의 인재를 <br> 매칭해드립니다.
            </div>
            <div>
                <div class=" footer-sub-title ">
                    010-0000-0000
                </div>
                <div class=" footer-sub-title">
                    aaaaa@naver.com
                </div>
            </div>
            <div class="q-pt-lg quick-links">

                <div class="quick-link">
                    <span class=" footer-sub-title">하이퍼하이어</span>
                    <span class="q-py-sm">김주현</span>
                </div>
                <div class="quick-link">
                    <span class=" footer-sub-title">대표 <strong>CEO</strong></span>
                    <span class="q-py-sm">상호명</span>

                </div>
            </div>
            <div class=" footer-sub-title">
                Hyperhire India Private LimitedJuhyun Kim
            </div>
            <div class="q-py-lg footer-sub-title ">ⓒ 2023 Hyperhire</div>
        </div>
        <div class="q-ml-xl">
            <div class="q-gutter-md">
                <div class="q-pa-sm row justify-start">
                    <!-- Iterate over the array of images and pass each item to MyCard component -->
                    <MyCard v-for="(item, index) in cardItems" :key="index" :image-src="item.src" :title="item.title"
                        :subTitle="item.subTitle" />

                </div>
            </div>
            <div class="q-gutter-md">
                    <div class="q-pa-sm row justify-center">
                    <div class="quick-link q-mx-lg">
                        <span class=" footer-sub-title">사업자등록번호 <strong>CIN</strong></span>
                        <span class="footer-sub-title q-py-sm">427-86-01187</span>
                        <span class="footer-sub-title">U74110DL2016PTC290812 </span>
                    </div>
                    <div class="quick-link ">
                        <span class=" footer-sub-title">주소 <strong>ADDRESS</strong></span>
                        <span class="q-py-sm">서울특별시 강남대로<strong>479,</strong> 지하 <strong>1</strong>층
                            <strong>238</strong>호</span>
                        <span class="footer-sub-title">D-138, Street number 11, Jagjeet Nagar, North East Delhi, New Delhi,
                            110053 India</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { ref } from 'vue';
import MyCard from '../components/MyCard.vue';

export default {
    components: {
        MyCard
    },
    setup() {
        // Define an array of objects containing image source and title
        const cardItems = ref([
            { src: '/icons/code_tag.png', title: ' 해외 개발자 원격 채용', subTitle: '바로가기' },
            { src: '/icons/person.png', title: '외국인 원격 채용 (비개발)', subTitle: '바로가기' },
            { src: '/icons/kor.png', title: '한국어 가능 외국인 채용', subTitle: '바로가기' },
            { src: '/icons/settings.png', title: '해외 개발자 활용 서비스', subTitle: '바로가기' }
            // Add more items as needed
        ]);

        return {
            cardItems
        };
    }
};
</script>
<style scoped>
.footer-container {
    display: flex;
    justify-content: flex-start;
    margin-left: 155px;
    padding: 50px 0px;
    color: #343741;
    background-color: #FBFBFB;
    ;

}

.footer-left {
    width: 20%;
}

.footer-sub-title {
    font-size: 12px;
    font-weight: bold;
}

.quick-links {
    display: flex;
    justify-content: space-between;
    width: 100%;
}

.sub-links {
    display: flex;
    justify-content: flex-start;
    width: 100%;
    margin: 0px 71px;
}

.quick-link {
    display: flex;
    flex-direction: column;
}
</style>