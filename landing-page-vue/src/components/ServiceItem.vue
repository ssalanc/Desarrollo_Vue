<script setup>
import Icon from './Icon.vue';

defineProps({
  icon: {
    type: String,
    required: true
  },
  title: {
    type: String,
    required: true
  },
  description: {
    type: String,
    required: true
  }
});
</script>

<template>
  <div class="service-item">
    <Icon :type="icon" size="large" />
    <h3>{{ title }}</h3>
    <p>{{ description }}</p>
  </div>
</template>

<style scoped>
.service-item {
  background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
  padding: 30px;
  border-radius: 8px;
  text-align: center;
  transition: all 0.3s ease;
  border-left: 4px solid #1abc9c;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.service-item:hover {
  transform: translateY(-10px);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.service-item h3 {
  font-size: 1.3rem;
  margin-bottom: 15px;
  color: #1a1a1a;
}

.service-item p {
  color: #666;
  line-height: 1.6;
}
</style>
