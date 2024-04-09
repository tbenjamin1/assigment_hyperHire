<template>
  <q-layout>
    <q-header unelevated class="text-white bg-white" height-hint="61.59">
      <q-toolbar class=" q-px-md justify-around" style="background-image: url('/icons/gradient.png');width:98%">
        <q-btn round dense flat :ripple="false" size="19px" color="white" class="q-mr-sm" no-caps>
          <img src="/icons/hyperhire.png" alt="Drop Image" class="drop-icon">
          <span class="q-px-sm">hyperhire</span>
        </q-btn>

        <div v-if="$q.screen.gt.sm"
          class="GL__toolbar-link q-ml-xs q-gutter-md text-body2 text-weight-bold row items-center no-wrap">
          <q-btn v-if="$q.screen.gt.xs" dense flat>
            <div class="row items-center no-wrap">
              <span>채용</span>
              <q-icon name="keyboard_arrow_down" />
            </div>
            <q-menu auto-close>
              <q-list dense style="min-width: 100px">
                <q-item clickable class="GL__menu-link">
                  <q-item-section class="">채용</q-item-section>
                </q-item>
                <q-item clickable class="GL__menu-link">
                  <q-item-section>해외 개발자 원격 채용</q-item-section>
                </q-item>
                <q-item clickable class="GL__menu-link">
                  <q-item-section>외국인 원격 채용 (비개발 직군)</q-item-section>
                </q-item>
                <q-item clickable class="GL__menu-link">
                  <q-item-section>한국어 가능 외국인 채용</q-item-section>
                </q-item>
              </q-list>
            </q-menu>
          </q-btn>
          <a href="javascript:void(0)" class="text-white">해외 개발자 활용 서비스</a>
        </div>
        <div class="q-pl-sm q-gutter-sm row items-center no-wrap">
          <q-btn unelevated v-if="$q.screen.gt.xs" color="white" text-color="blue" label="문의하기"></q-btn>
        </div>
      </q-toolbar>
    </q-header>

    <!-- Body -->
    <q-page-container style="background-image: url('/icons/gradient.png');width:98%">
      <IndexPage />
    </q-page-container>

    <!-- Bottom -->
    <q-footer class="text-blue bg-white">
      <BottomFooter />
    </q-footer>
  </q-layout>
</template>

<script>
import { fabGithub } from '@quasar/extras/fontawesome-v6'
import IndexPage from '../pages/IndexPage.vue';
import BottomFooter from '../pages/BottomFooter.vue';

export default {
  name: 'MyLayout',
  components: {
    IndexPage,
    BottomFooter,
  },
  data() {
    return {
      text: '',
      fabGithub: fabGithub
    }
  },
  mounted() {

  },
  methods: {


  }
}
</script>

<style scoped>
.q-layout {
  min-height: unset !important;
}

@media (max-width: 600px) {
  .q-page-container {
    width: 100% !important;
  }

  .q-toolbar {
    width: 100% !important;
    display: flex;
    justify-content: flex-start;
  }
}
</style>
