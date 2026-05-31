<script setup>
import { ref, computed } from 'vue';
import Button from './Button.vue';
import Modal from './Modal.vue';

const destinations = [
  { id: 1, title: 'París, Francia' },
  { id: 2, title: 'Tokio, Japón' },
  { id: 3, title: 'Nueva York, USA' },
  { id: 4, title: 'Bali, Indonesia' },
  { id: 5, title: 'Barcelona, España' },
  { id: 6, title: 'Sídney, Australia' }
];

const form = ref({
  name: '',
  email: '',
  phone: '',
  destination: '',
  message: ''
});

const touched = ref({
  name: false,
  email: false,
  phone: false,
  destination: false,
  message: false
});

const modalOpen = ref(false);

// Validaciones
const nameError = computed(() => {
  if (!form.value.name) return 'El nombre es requerido';
  if (form.value.name.length < 3) return 'El nombre debe tener al menos 3 caracteres';
  return '';
});

const emailError = computed(() => {
  if (!form.value.email) return 'El email es requerido';
  const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  if (!emailRegex.test(form.value.email)) return 'Email inválido';
  return '';
});

const phoneError = computed(() => {
  if (!form.value.phone) return 'El teléfono es requerido';
  const phoneRegex = /^[0-9+\-\s()]+$/;
  if (!phoneRegex.test(form.value.phone)) return 'Solo números, +, -, espacios y paréntesis';
  if (form.value.phone.replace(/\D/g, '').length < 7) return 'Teléfono muy corto';
  return '';
});

const destinationError = computed(() => {
  if (!form.value.destination) return 'Selecciona un destino';
  return '';
});

const messageError = computed(() => {
  if (!form.value.message) return 'El mensaje es requerido';
  if (form.value.message.length < 10) return 'Mínimo 10 caracteres';
  return '';
});

const isFormValid = computed(() => {
  return !nameError.value && !emailError.value && !phoneError.value && !destinationError.value && !messageError.value;
});

const handleSubmit = (e) => {
  e.preventDefault();

  if (!isFormValid.value) return;

  console.log('Datos del formulario:', form.value);
  modalOpen.value = true;
  form.value = { name: '', email: '', phone: '', destination: '', message: '' };
};
</script>

<template>
  <div class="contact-container">
    <h2>¿Necesitas Ayuda?</h2>
    <form class="contact-form" @submit="handleSubmit">
      <div class="form-group">
        <label for="name">Nombre Completo</label>
        <input
          v-model="form.name"
          @input="touched.name = true"
          type="text"
          id="name"
          placeholder="Juan Pérez"
        />
        <span v-if="touched.name && nameError" class="error-message">{{ nameError }}</span>
      </div>

      <div class="form-group">
        <label for="email">Correo Electrónico</label>
        <input
          v-model="form.email"
          @input="touched.email = true"
          type="email"
          id="email"
          placeholder="tu@email.com"
        />
        <span v-if="touched.email && emailError" class="error-message">{{ emailError }}</span>
      </div>

      <div class="form-group">
        <label for="phone">Teléfono</label>
        <input
          v-model="form.phone"
          @input="touched.phone = true"
          type="tel"
          id="phone"
          placeholder="+34 612 345 678"
        />
        <span v-if="touched.phone && phoneError" class="error-message">{{ phoneError }}</span>
      </div>

      <div class="form-group">
        <label for="destination">Destino Preferido</label>
        <select v-model="form.destination" @change="touched.destination = true" id="destination">
          <option value="">Selecciona un destino</option>
          <option v-for="dest in destinations" :key="dest.id" :value="dest.title">
            {{ dest.title }}
          </option>
        </select>
        <span v-if="touched.destination && destinationError" class="error-message">{{ destinationError }}</span>
      </div>

      <div class="form-group">
        <label for="message">Mensaje</label>
        <textarea
          v-model="form.message"
          @input="touched.message = true"
          id="message"
          rows="5"
          placeholder="Cuéntanos sobre tu viaje soñado..."
        ></textarea>
        <span v-if="touched.message && messageError" class="error-message">{{ messageError }}</span>
      </div>

      <Button type="submit" variant="primary" size="large" :disabled="!isFormValid">
        Enviar Consulta
      </Button>
    </form>

    <Modal
      :isOpen="modalOpen"
      title="¡Consulta enviada!"
      message="¡Gracias por tu consulta! Nos pondremos en contacto pronto."
      type="success"
      @close="modalOpen = false"
    />
  </div>
</template>

<style scoped>
.contact-container {
  background-color: white;
  padding: 4rem 2rem;
}

.contact-container h2 {
  text-align: center;
  margin-bottom: 40px;
  font-size: 2.5rem;
  color: #1a1a1a;
}

.contact-form {
  max-width: 600px;
  margin: 0 auto;
  background-color: #f9f9f9;
  padding: 40px;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.form-group {
  margin-bottom: 20px;
  display: flex;
  flex-direction: column;
}

.form-group label {
  font-weight: 600;
  margin-bottom: 8px;
  color: #1a1a1a;
}

.form-group input,
.form-group select,
.form-group textarea {
  padding: 12px;
  border: 1px solid #ddd;
  border-radius: 8px;
  font-size: 1rem;
  font-family: inherit;
  transition: all 0.3s ease;
}

.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #007bff;
  box-shadow: 0 0 8px rgba(0, 123, 255, 0.3);
}

.form-group input::placeholder {
  color: #999;
}

.error-message {
  color: #ff6b6b;
  font-size: 0.875rem;
  margin-top: 4px;
  display: block;
}

.contact-form > button {
  width: 100%;
  margin-top: 10px;
}

.contact-form > button:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}

@media (max-width: 768px) {
  .contact-container {
    padding: 2rem 1rem;
  }

  .contact-form {
    padding: 20px;
  }

  .contact-container h2 {
    font-size: 2rem;
  }
}
</style>
