<script setup>
import { ref } from 'vue';
import MainLayout from './layouts/MainLayout.vue'
import Home from './pages/Home.vue'
import DesignSystem from './pages/DesignSystem.vue'

const currentPage = ref('home');

const handleNavigation = (page) => {
  currentPage.value = page;
  window.scrollTo(0, 0);
};
</script>

<template>
  <MainLayout :currentPage="currentPage" @navigate="handleNavigation">
    <Home v-if="currentPage === 'home'" />
    <DesignSystem v-else-if="currentPage === 'design-system'" />
  </MainLayout>
</template>
