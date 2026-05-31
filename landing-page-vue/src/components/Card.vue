<script setup>
defineProps({
  image: String,
  title: String,
  description: String,
  price: Number,
  rating: Number
});
</script>

<template>
  <div class="card">
    <div class="card-image">
      <img :src="image" :alt="title" />
      <div v-if="rating" class="card-rating">
        <i class="fas fa-star"></i>
        <span>{{ rating }}</span>
      </div>
    </div>
    <div class="card-content">
      <h3 class="card-title">{{ title }}</h3>
      <p class="card-description">{{ description }}</p>
      <div v-if="price" class="card-footer">
        <span class="card-price">${{ price }}</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  background: white;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  display: flex;
  flex-direction: column;
  height: 100%;
}

.card:hover {
  transform: translateY(-8px);
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.15);
}

.card-image {
  position: relative;
  width: 100%;
  height: 200px;
  overflow: hidden;
}

.card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.card:hover .card-image img {
  transform: scale(1.05);
}

.card-rating {
  position: absolute;
  top: 12px;
  right: 12px;
  background: rgba(255, 215, 0, 0.95);
  color: #333;
  padding: 6px 12px;
  border-radius: 24px;
  display: flex;
  align-items: center;
  gap: 6px;
  font-weight: bold;
  font-size: 14px;
}

.card-rating i {
  font-size: 14px;
}

.card-content {
  padding: 20px;
  flex: 1;
  display: flex;
  flex-direction: column;
}

.card-title {
  margin: 0 0 12px 0;
  font-size: 18px;
  font-weight: 600;
  color: #333;
}

.card-description {
  margin: 0 0 auto 0;
  font-size: 14px;
  color: #666;
  line-height: 1.5;
}

.card-footer {
  margin-top: 12px;
  padding-top: 12px;
  border-top: 1px solid #e0e0e0;
}

.card-price {
  font-size: 18px;
  font-weight: bold;
  color: #1abc9c;
}
</style>
