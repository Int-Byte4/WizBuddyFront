<template>
  <AppHeader v-if="!(isWelcomePage)"/>
  <main>
    <RouterView/>  <!-- 라우트에 따라 페이지가 출력됨 -->
  </main>
  
  <!-- v-if로 LoginPage일 경우에는 AppFooter가 보이지 않도록 함 -->
  <AppFooter v-if="!(isLoginPage|isSignupPage|isWelcomePage)"/>    <!-- 푸터 컴포넌트 -->

</template>

<script setup>
import './assets/css/style.css';
import { RouterView, useRoute } from 'vue-router';
import {ref, watch} from 'vue';


import AppHeader from '@/components/AppHeader.vue';
import AppFooter from '@/components/AppFooter.vue';

const route = useRoute();

const isLoginPage = ref(false);
const isSignupPage = ref(false);
const isMainPage = ref(false);
const isSchedulePage = ref(false);
const isCheckListPage = ref(false);
const isNoticeBoardPage = ref(false);
const isManualBoardPage = ref(false);
const isSubsBoardPage = ref(false);
const isWelcomePage = ref(false);

watch(() => route.path, (newPath) => {
  isWelcomePage.value = newPath === '/';
  isLoginPage.value = newPath === '/login';
  isSignupPage.value = newPath === '/signup';
  isMainPage.value = newPath === '/main';
  isSchedulePage.value = newPath === '/schedule';
  isCheckListPage.value = newPath === '/checklist';
  isNoticeBoardPage.value = newPath === '/noticeboard';
  isManualBoardPage.value = newPath === '/manualboard';
  isSubsBoardPage.value = newPath === '/subsboard';
},
{ 
  immediate: true 
}); 
</script> 

<style scoped>
</style>

