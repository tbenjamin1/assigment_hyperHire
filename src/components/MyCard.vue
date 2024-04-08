<template>
    <q-card class="my-card" flat bordered>
        <div class="q-pa-sm">
            <q-avatar rounded size="24px"> <img :src="imageSrc" class="rounded-img"></q-avatar>
        </div>
        <q-card-actions class="q-pa-sm">

            <div class="col">
                <div class=" text-weight-bold text-black text-capitalize main-title">{{ title }}</div>
                <div class="text-subtitle text-capitalize"> <span>{{ subTitle }}</span> <img src="/icons/ArrowRightSquare.png" class="q-ma-sm" alt="">
                </div>
            </div>
        </q-card-actions>
    </q-card>
</template>
<script>
export default {
    props: {
        imageSrc: String,
        title: String,
        subTitle: String,
    }
};
</script>

<style scoped>
.my-main-card {
    width: 23%;
}

.q-card {
    border-radius: none;
    margin: 10px;
}

.q-card--bordered {
    border: none;
}

.main-title {
    font-size: 12px;
}

.text-subtitle {
    font-size: 12px;
    display: flex;
    justify-items: center;
    align-items: center;
}
</style>