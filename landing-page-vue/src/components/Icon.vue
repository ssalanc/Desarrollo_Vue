<script setup>
import { computed } from 'vue';

const props = defineProps({
  type: String,
  size: {
    type: String,
    default: 'medium'
  }
});

const iconMap = {
  flights: 'fa-plane-departure',
  hotel: 'fa-hotel',
  car: 'fa-car',
  compass: 'fa-compass'
};

const sizeClasses = {
  small: 'icon-small',
  medium: 'icon-medium',
  large: 'icon-large'
};

const iconClass = computed(() => iconMap[props.type] || '');
const sizeClass = computed(() => sizeClasses[props.size] || 'icon-medium');
</script>

<template>
  <div :class="`icon ${sizeClass}`">
    <i v-if="iconClass" :class="`fas ${iconClass}`"></i>
  </div>
</template>

<style scoped>
.icon {
  display: flex;
  align-items: center;
  justify-content: center;
}

.icon i {
  color: #1abc9c;
}

.icon-small {
  width: 24px;
  height: 24px;
}

.icon-small i {
  font-size: 24px;
}

.icon-medium {
  width: 40px;
  height: 40px;
}

.icon-medium i {
  font-size: 40px;
}

.icon-large {
  width: 60px;
  height: 60px;
}

.icon-large i {
  font-size: 60px;
}
</style>
