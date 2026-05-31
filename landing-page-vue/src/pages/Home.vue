<script setup>
import Card from '../components/Card.vue';
import Icon from '../components/Icon.vue';
import ContactForm from '../components/ContactForm.vue';
import Button from '../components/Button.vue';

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
  { title: 'Vuelos Internacionales', description: 'Acceso a vuelos de las mejores aerolíneas del mundo', icon: 'flights' },
  { title: 'Hospedaje Premium', description: 'Alojamiento en hoteles de lujo seleccionados', icon: 'hotel' },
  { title: 'Alquiler de Autos', description: 'Vehículos de calidad para explorar a tu ritmo', icon: 'car' },
  { title: 'Tours Guiados', description: 'Experiencias culturales con guías profesionales', icon: 'compass' }
];

const scrollToForm = () => {
  const contactSection = document.getElementById('contacto');
  contactSection?.scrollIntoView({ behavior: 'smooth' });
};
</script>

<template>
  <div class="home">
    <!-- Hero Section -->
    <section id="home" class="hero">
      <div class="hero-content">
        <h1>Descubre el Mundo con TravelGo</h1>
        <p>Tus aventuras soñadas comenzarán aquí. Explora destinos increíbles a precios inigualables.</p>
        <Button variant="secondary" size="large" @click="scrollToForm">
          Contáctenos
        </Button>
      </div>
    </section>

    <!-- Servicios -->
    <section id="servicios" class="services section-padding">
      <div class="container">
        <h2>Nuestros Servicios</h2>
        <div class="services-grid">
          <div v-for="(service, idx) in services" :key="idx" class="service-item">
            <Icon :type="service.icon" size="large" />
            <h3>{{ service.title }}</h3>
            <p>{{ service.description }}</p>
          </div>
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

/* Hero Section */
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
}

.hero-content {
  max-width: 1000px;
  text-align: center;
}

.hero-content h1 {
  font-size: 3.5rem;
  margin-bottom: 20px;
  animation: fadeInDown 0.8s ease;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
  white-space: normal;
  word-spacing: 100vw;
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
    word-spacing: normal;
  }

  .hero-content p {
    font-size: 1rem;
  }

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
