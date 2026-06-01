<script setup>
import Button from './Button.vue';

defineProps({
  onContactClick: {
    type: Function,
    required: true
  }
});
</script>

<template>
  <section id="home" class="hero">
    <div class="hero-content">
      <h1>Descubre el Mundo con TravelGo</h1>
      <p>Tus aventuras soñadas comenzarán aquí. Explora destinos increíbles a precios inigualables.</p>
      <Button variant="primary" size="large" @click="onContactClick">
        Contáctenos
      </Button>
    </div>
  </section>
</template>

<style scoped>
.hero {
  background: url('https://images.unsplash.com/photo-1488646953014-85cb44e25828?w=1200&h=600&fit=crop') center/cover no-repeat;
  background-attachment: fixed;
  color: white;
  padding: 120px 20px;
  text-align: center;
  min-height: 600px;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
}

.hero-content {
  max-width: none;
  width: 100%;
  text-align: center;
  padding: 0 20px;
}

.hero-content h1 {
  font-size: 3.5rem;
  margin-bottom: 20px;
  animation: fadeInDown 0.8s ease;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
  white-space: nowrap;
  overflow: hidden;
  text-overflow: clip;
}

.hero-content p {
  font-size: 1.25rem;
  margin-bottom: 30px;
  animation: fadeInUp 0.8s ease;
  text-shadow: 1px 1px 3px rgba(255, 255, 255, 0.5);
  color: #000;
  font-weight: 500;
}

@keyframes fadeInDown {
  from {
    opacity: 0;
    transform: translateY(-30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Responsive */
@media (max-width: 768px) {
  .hero {
    padding: 60px 20px;
    min-height: auto;
  }

  .hero-content {
    max-width: 100%;
    padding: 0 20px;
  }

  .hero-content h1 {
    font-size: 1.8rem;
    white-space: normal;
    overflow: visible;
  }

  .hero-content p {
    font-size: 1rem;
  }
}
</style>
