<script setup>
import Navigation from '../components/Navigation.vue';
import Footer from '../components/Footer.vue';

defineProps({
  currentPage: String
});

defineEmits(['navigate']);
</script>

<template>
  <div class="main-layout">
    <Navigation :currentPage="currentPage" @navigate="$emit('navigate', $event)" />
    <main class="main-content">
      <slot></slot>
    </main>
    <Footer />
  </div>
</template>

<style scoped>
.main-layout {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.main-content {
  flex: 1;
}
</style>
