<script setup>
import { ref } from 'vue';

const isMenuOpen = ref(false);

defineProps({
  currentPage: String
});

const emit = defineEmits(['navigate']);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};

const handleDesignSystemClick = (e) => {
  e.preventDefault();
  emit('navigate', 'design-system');
  isMenuOpen.value = false;
};

const handleMenuClick = () => {
  isMenuOpen.value = false;
};
</script>

<template>
  <nav class="navbar">
    <div class="navbar-container">
      <div class="navbar-logo">
        <a href="#home">
          TravelGo
        </a>
      </div>

      <div :class="`navbar-menu ${isMenuOpen ? 'active' : ''}`">
        <a href="#home" @click="handleMenuClick" class="nav-link">
          Inicio
        </a>
        <a href="#destinos" @click="handleMenuClick" class="nav-link">
          Destinos
        </a>
        <a href="#servicios" @click="handleMenuClick" class="nav-link">
          Servicios
        </a>
        <a href="#contacto" @click="handleMenuClick" class="nav-link">
          Contacto
        </a>
        <a href="#design-system" @click="handleDesignSystemClick" :class="`nav-link ${currentPage === 'design-system' ? 'active' : ''}`">
          Design System
        </a>
      </div>

      <div class="hamburger" @click="toggleMenu">
        <span :class="{ active: isMenuOpen }"></span>
        <span :class="{ active: isMenuOpen }"></span>
        <span :class="{ active: isMenuOpen }"></span>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  background: white;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  position: sticky;
  top: 0;
  z-index: 100;
}

.navbar-container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
}

.navbar-logo a {
  font-size: 24px;
  font-weight: bold;
  color: #1abc9c;
  text-decoration: none;
  transition: color 0.3s ease;
}

.navbar-logo a:hover {
  color: #16a085;
}

.navbar-menu {
  display: flex;
  gap: 2rem;
  margin-left: auto;
}

.nav-link {
  color: #333;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
}

.nav-link:hover {
  color: #1abc9c;
}

.nav-link.active {
  color: #1abc9c;
  font-weight: 600;
  border-bottom: 2px solid #1abc9c;
  padding-bottom: 4px;
}

.hamburger {
  display: none;
  flex-direction: column;
  cursor: pointer;
  gap: 6px;
}

.hamburger span {
  width: 25px;
  height: 3px;
  background: #333;
  border-radius: 2px;
  transition: all 0.3s ease;
}

.hamburger span.active:nth-child(1) {
  transform: rotate(45deg) translate(10px, 10px);
}

.hamburger span.active:nth-child(2) {
  opacity: 0;
}

.hamburger span.active:nth-child(3) {
  transform: rotate(-45deg) translate(7px, -7px);
}

@media (max-width: 768px) {
  .hamburger {
    display: flex;
  }

  .navbar-container {
    padding: 1rem 1rem;
  }

  .navbar-menu {
    display: none;
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    flex-direction: column;
    background: white;
    padding: 0;
    gap: 0;
    overflow: hidden;
    transition: all 0.3s ease;
    width: 100%;
  }

  .navbar-menu.active {
    display: flex;
    padding: 0;
    gap: 0;
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
  }

  .nav-link {
    padding: 12px 1rem;
    display: block;
    width: 100%;
  }
}
</style>
