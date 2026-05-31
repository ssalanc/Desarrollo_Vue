<script setup>
import Navigation from '../components/Navigation.vue';
import Footer from '../components/Footer.vue';
</script>

<template>
  <div class="main-layout">
    <Navigation />
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
