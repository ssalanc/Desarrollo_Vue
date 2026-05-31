<script setup>
import { ref } from 'vue';
import Button from '../components/Button.vue';
import Card from '../components/Card.vue';
import Icon from '../components/Icon.vue';
import Modal from '../components/Modal.vue';
import Navigation from '../components/Navigation.vue';
import ContactForm from '../components/ContactForm.vue';

const modalOpen = ref(false);

const colors = [
  { name: 'Primary', variable: '--primary-color', hex: '#1abc9c' },
  { name: 'Accent', variable: '--accent-color', hex: '#ffc107' },
  { name: 'Dark', variable: '--dark-color', hex: '#1a1a1a' },
  { name: 'Light', variable: '--light-color', hex: '#f9f9f9' }
];

const typography = [
  { element: 'h1', text: 'Heading 1 - 3rem', size: '3rem', weight: 700 },
  { element: 'h2', text: 'Heading 2 - 2rem', size: '2rem', weight: 700 },
  { element: 'h3', text: 'Heading 3 - 1.5rem', size: '1.5rem', weight: 700 },
  { element: 'p', text: 'Body Text - 1rem', size: '1rem', weight: 400 },
  { element: 'small', text: 'Small Text - 0.875rem', size: '0.875rem', weight: 400 }
];

const buttonVariants = ['primary'];
const buttonSizes = ['small', 'medium', 'large'];

const spacing = [
  { name: '8px', value: '8px' },
  { name: '12px', value: '12px' },
  { name: '16px', value: '16px' },
  { name: '24px', value: '24px' },
  { name: '32px', value: '32px' },
  { name: '60px', value: '60px' }
];

const cardExample = {
  image: 'https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=300&h=200&fit=crop',
  title: 'Mountain Adventure',
  description: 'Explore beautiful mountain landscapes',
  price: 99.99,
  rating: 4.5
};

const iconTypes = ['flights', 'hotel', 'car', 'compass'];
</script>

<template>
  <div class="design-system-container">
    <nav class="ds-nav">
      <h1>Design System</h1>
      <p>Componentes, colores y estilos del proyecto</p>
    </nav>

    <div class="ds-content">
      <!-- PALETA DE COLORES -->
      <section class="ds-section">
        <h2>Paleta de Colores</h2>
        <div class="colors-grid">
          <div v-for="color in colors" :key="color.variable" class="color-card">
            <div class="color-box" :style="{ backgroundColor: color.hex }"></div>
            <h4>{{ color.name }}</h4>
            <p class="color-hex">{{ color.hex }}</p>
            <p class="color-var">{{ color.variable }}</p>
          </div>
        </div>
      </section>

      <!-- TIPOGRAFÍA -->
      <section class="ds-section">
        <h2>Tipografía</h2>
        <div class="typography-grid">
          <div v-for="(type, idx) in typography" :key="idx" class="typography-item">
            <component :is="type.element" class="typography-sample">
              {{ type.text }}
            </component>
            <p class="typography-info">
              Size: {{ type.size }} | Weight: {{ type.weight }}
            </p>
          </div>
        </div>
      </section>

      <!-- ESPACIADO -->
      <section class="ds-section">
        <h2>Espaciado</h2>
        <div class="spacing-grid">
          <div v-for="space in spacing" :key="space.value" class="spacing-item">
            <div
              class="spacing-box"
              :style="{ width: space.value, height: space.value }"
            ></div>
            <p>{{ space.name }}</p>
          </div>
        </div>
      </section>

      <!-- BOTONES -->
      <section class="ds-section">
        <h2>Botones</h2>

        <div class="ds-subsection">
          <h3>Variantes</h3>
          <div class="buttons-grid">
            <div v-for="variant in buttonVariants" :key="variant" class="button-group">
              <h4 class="button-variant-title">{{ variant }}</h4>
              <div class="button-demo">
                <Button :variant="variant" size="medium">
                  {{ variant.charAt(0).toUpperCase() + variant.slice(1) }}
                </Button>
              </div>
            </div>
          </div>
        </div>

        <div class="ds-subsection">
          <h3>Tamaños</h3>
          <div class="buttons-grid">
            <div v-for="size in buttonSizes" :key="size" class="button-group">
              <h4 class="button-variant-title">{{ size }}</h4>
              <div class="button-demo">
                <Button variant="primary" :size="size">
                  {{ size.charAt(0).toUpperCase() + size.slice(1) }}
                </Button>
              </div>
            </div>
          </div>
        </div>

        <div class="ds-subsection">
          <h3>Estados</h3>
          <div class="buttons-grid">
            <div class="button-group">
              <h4 class="button-variant-title">Activo</h4>
              <div class="button-demo">
                <Button variant="primary">Click me</Button>
              </div>
            </div>
            <div class="button-group">
              <h4 class="button-variant-title">Deshabilitado</h4>
              <div class="button-demo">
                <Button variant="primary" disabled>
                  Disabled
                </Button>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- TARJETAS -->
      <section class="ds-section">
        <h2>Tarjetas</h2>
        <div class="cards-grid">
          <Card v-bind="cardExample" />
          <Card v-bind="cardExample" />
          <Card v-bind="cardExample" />
        </div>
      </section>

      <!-- ICONOS -->
      <section class="ds-section">
        <h2>Iconos</h2>

        <div class="ds-subsection">
          <h3>Tamaños</h3>
          <div class="icons-grid">
            <div v-for="size in ['small', 'medium', 'large']" :key="size" class="icon-group">
              <h4 class="icon-size-title">{{ size }}</h4>
              <Icon type="flights" :size="size" />
            </div>
          </div>
        </div>

        <div class="ds-subsection">
          <h3>Tipos</h3>
          <div class="icons-grid">
            <div v-for="type in iconTypes" :key="type" class="icon-group">
              <h4 class="icon-type-title">{{ type }}</h4>
              <Icon :type="type" size="medium" />
            </div>
          </div>
        </div>
      </section>

      <!-- MODAL -->
      <section class="ds-section">
        <h2>Modal</h2>
        <div class="modal-demo">
          <Button variant="primary" @click="modalOpen = true">
            Abrir Modal
          </Button>
          <Modal
            :isOpen="modalOpen"
            title="Modal Ejemplo"
            message="Este es un ejemplo del componente Modal"
            type="success"
            @close="modalOpen = false"
          />
        </div>
      </section>

      <!-- FORMULARIO -->
      <section class="ds-section">
        <h2>Formulario de Contacto</h2>
        <div class="form-demo">
          <ContactForm />
        </div>
      </section>

      <!-- NAVEGACIÓN -->
      <section class="ds-section">
        <h2>Navegación</h2>
        <Navigation />
      </section>
    </div>
  </div>
</template>

<style scoped>
.design-system-container {
  min-height: 100vh;
  background-color: #f9f9f9;
}

.ds-nav {
  background: linear-gradient(135deg, var(--primary-color) 0%, #16a085 100%);
  color: white;
  padding: 60px 20px;
  text-align: center;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.ds-nav h1 {
  font-size: 3rem;
  margin-bottom: 10px;
}

.ds-nav p {
  font-size: 1.1rem;
  opacity: 0.9;
}

.ds-content {
  max-width: 1400px;
  margin: 0 auto;
  padding: 40px 20px;
}

.ds-section {
  background: white;
  border-radius: 12px;
  padding: 40px;
  margin-bottom: 40px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.ds-section h2 {
  font-size: 2rem;
  margin-bottom: 30px;
  color: var(--dark-color);
  border-bottom: 3px solid var(--primary-color);
  padding-bottom: 15px;
}

.ds-subsection {
  margin-bottom: 40px;
}

.ds-subsection h3 {
  font-size: 1.25rem;
  margin-bottom: 20px;
  color: var(--dark-color);
  margin-top: 30px;
}

.colors-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
}

.color-card {
  text-align: center;
  background: #f9f9f9;
  padding: 20px;
  border-radius: 8px;
}

.color-box {
  width: 100%;
  height: 120px;
  border-radius: 8px;
  margin-bottom: 15px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.color-card h4 {
  margin: 10px 0;
  color: var(--dark-color);
}

.color-hex {
  font-family: 'Courier New', monospace;
  font-weight: 600;
  color: var(--dark-color);
  margin-bottom: 5px;
}

.color-var {
  font-family: 'Courier New', monospace;
  font-size: 0.875rem;
  color: #666;
}

.typography-grid {
  display: grid;
  gap: 30px;
}

.typography-item {
  padding: 20px;
  background: #f9f9f9;
  border-radius: 8px;
}

.typography-sample {
  margin: 0;
}

.typography-info {
  font-size: 0.875rem;
  color: #666;
  margin-top: 10px;
}

.spacing-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 30px;
}

.spacing-item {
  text-align: center;
}

.spacing-box {
  background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
  margin: 0 auto 15px;
  border-radius: 4px;
}

.spacing-item p {
  font-family: 'Courier New', monospace;
  font-weight: 600;
  color: var(--dark-color);
}

.buttons-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 30px;
}

.button-group {
  text-align: center;
}

.button-variant-title,
.icon-size-title,
.icon-type-title {
  font-size: 0.95rem;
  text-transform: capitalize;
  margin-bottom: 15px;
  color: #666;
  font-weight: 600;
}

.button-demo {
  background: #f9f9f9;
  padding: 30px;
  border-radius: 8px;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100px;
}

.cards-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
}

.icons-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 30px;
}

.icon-group {
  text-align: center;
  background: #f9f9f9;
  padding: 30px;
  border-radius: 8px;
}

.modal-demo {
  background: #f9f9f9;
  padding: 40px;
  border-radius: 8px;
  text-align: center;
}

.form-demo {
  background: #f9f9f9;
  padding: 30px;
  border-radius: 8px;
}

@media (max-width: 768px) {
  .ds-nav h1 {
    font-size: 2rem;
  }

  .ds-nav p {
    font-size: 1rem;
  }

  .ds-section {
    padding: 30px 20px;
  }

  .colors-grid,
  .buttons-grid,
  .cards-grid,
  .icons-grid {
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  }
}
</style>
