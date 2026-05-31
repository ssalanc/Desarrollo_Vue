<script setup>
defineProps({
  variant: {
    type: String,
    default: 'primary'
  },
  size: {
    type: String,
    default: 'medium'
  },
  disabled: {
    type: Boolean,
    default: false
  },
  type: {
    type: String,
    default: 'button'
  }
});

defineEmits(['click']);
</script>

<template>
  <button
    :class="`btn btn-${variant} btn-${size}`"
    :disabled="disabled"
    :type="type"
    @click="$emit('click')"
  >
    <slot></slot>
  </button>
</template>

<style scoped>
.btn {
  padding: 12px 24px;
  border: none;
  border-radius: 6px;
  font-size: 16px;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  text-decoration: none;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
}

.btn:disabled {
  opacity: 0.6;
  cursor: not-allowed;
}

/* Variants */
.btn-primary {
  background: linear-gradient(135deg, #1abc9c 0%, #16a085 100%);
  color: white;
}

.btn-primary:hover:not(:disabled) {
  background: linear-gradient(135deg, #16a085 0%, #138070 100%);
  box-shadow: 0 4px 12px rgba(26, 188, 156, 0.3);
}


/* Sizes */
.btn-small {
  padding: 8px 16px;
  font-size: 14px;
}

.btn-medium {
  padding: 12px 24px;
  font-size: 16px;
}

.btn-large {
  padding: 16px 32px;
  font-size: 18px;
  min-width: 200px;
}
</style>
