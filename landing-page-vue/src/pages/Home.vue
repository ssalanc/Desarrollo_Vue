<script setup>
import Card from '../components/Card.vue';
import ContactForm from '../components/ContactForm.vue';
import Hero from '../components/Hero.vue';
import ServiceItem from '../components/ServiceItem.vue';

const destinations = [
  {
    id: 1,
    image: 'https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=400&h=250&fit=crop',
    title: 'París, Francia',
    description: 'Explora la ciudad del amor con sus monumentos icónicos y gastronomía deliciosa.',
    price: 1200,
    rating: 4.8
  },
  {
    id: 2,
    image: 'https://images.unsplash.com/photo-1488646953014-85cb44e25828?w=400&h=250&fit=crop',
    title: 'Tokio, Japón',
    description: 'Sumérgete en la fusión de lo tradicional y lo moderno en esta vibrante metrópolis.',
    price: 1500,
    rating: 4.9
  },
  {
    id: 3,
    image: 'https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=400&h=250&fit=crop',
    title: 'Nueva York, USA',
    description: 'La ciudad que nunca duerme te espera con sus rascacielos y vida nocturna.',
    price: 1100,
    rating: 4.7
  },
  {
    id: 4,
    image: 'https://images.unsplash.com/photo-1533900298318-6b8da08a523e?w=400&h=250&fit=crop',
    title: 'Bali, Indonesia',
    description: 'Playas exóticas, templos antiguos y paisajes paradisíacos te esperan.',
    price: 900,
    rating: 4.8
  },
  {
    id: 5,
    image: 'https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=400&h=250&fit=crop',
    title: 'Barcelona, España',
    description: 'Arte, arquitectura y vida mediterránea en la perla de Cataluña.',
    price: 950,
    rating: 4.6
  },
  {
    id: 6,
    image: 'https://images.unsplash.com/photo-1488646953014-85cb44e25828?w=400&h=250&fit=crop',
    title: 'Sídney, Australia',
    description: 'Playas vírgenes, fauna única y aventura en el fin del mundo.',
    price: 1800,
    rating: 4.9
  }
];

const services = [
  { id: 1, title: 'Vuelos Internacionales', description: 'Acceso a vuelos de las mejores aerolíneas del mundo', icon: 'flights' },
  { id: 2, title: 'Hospedaje Premium', description: 'Alojamiento en hoteles de lujo seleccionados', icon: 'hotel' },
  { id: 3, title: 'Alquiler de Autos', description: 'Vehículos de calidad para explorar a tu ritmo', icon: 'car' },
  { id: 4, title: 'Tours Guiados', description: 'Experiencias culturales con guías profesionales', icon: 'compass' }
];

const scrollToForm = () => {
  const contactSection = document.getElementById('contacto');
  contactSection?.scrollIntoView({ behavior: 'smooth' });
};
</script>

<template>
  <div class="home">
    <!-- Hero Section -->
    <Hero :onContactClick="scrollToForm" />

    <!-- Servicios -->
    <section id="servicios" class="services section-padding">
      <div class="container">
        <h2>Nuestros Servicios</h2>
        <div class="services-grid">
          <ServiceItem
            v-for="service in services"
            :key="service.id"
            :icon="service.icon"
            :title="service.title"
            :description="service.description"
          />
        </div>
      </div>
    </section>

    <!-- Destinos -->
    <section id="destinos" class="destinations section-padding">
      <div class="container">
        <h2>Destinos Populares</h2>
        <div class="destinations-grid">
          <Card
            v-for="destination in destinations"
            :key="destination.id"
            :image="destination.image"
            :title="destination.title"
            :description="destination.description"
            :price="destination.price"
            :rating="destination.rating"
          />
        </div>
      </div>
    </section>

    <!-- Formulario de Contacto -->
    <section id="contacto">
      <ContactForm />
    </section>
  </div>
</template>

<style scoped>
.home {
  width: 100%;
}

/* Services Section */
.services {
  background-color: white;
}

.services h2 {
  text-align: center;
  margin-bottom: 50px;
  font-size: 2.5rem;
  color: #1a1a1a;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 30px;
}

/* Destinations Section */
.destinations {
  background-color: #f9f9f9;
}

.destinations h2 {
  text-align: center;
  margin-bottom: 50px;
  font-size: 2.5rem;
  color: #1a1a1a;
}

.destinations-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
}

/* Utilities */
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.section-padding {
  padding: 4rem 2rem;
}

/* Responsive */
@media (max-width: 768px) {
  .services h2,
  .destinations h2 {
    font-size: 2rem;
  }

  .destinations-grid {
    grid-template-columns: 1fr;
  }

  .services-grid {
    grid-template-columns: 1fr;
  }
}
</style>
