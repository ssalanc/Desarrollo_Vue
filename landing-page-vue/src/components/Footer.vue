<script setup>
</script>

<template>
  <footer class="footer">
    <div class="footer-container">
      <div class="footer-section">
        <h4>Sobre TravelGo</h4>
        <p>Tus viajes soñados, a solo un clic de distancia. Descubre el mundo con nosotros.</p>
      </div>
      <div class="footer-section">
        <h4>Enlaces Rápidos</h4>
        <ul>
          <li><a href="#destinos">Destinos</a></li>
          <li><a href="#servicios">Servicios</a></li>
          <li><a href="#contacto">Contacto</a></li>
        </ul>
      </div>
      <div class="footer-section">
        <h4>Redes Sociales</h4>
        <div class="social-links">
          <a href="#facebook" title="Facebook" class="social-icon">
            <i class="fab fa-facebook"></i>
          </a>
          <a href="#twitter" title="Twitter" class="social-icon">
            <i class="fab fa-twitter"></i>
          </a>
          <a href="#instagram" title="Instagram" class="social-icon">
            <i class="fab fa-instagram"></i>
          </a>
        </div>
      </div>
    </div>
    <div class="footer-bottom">
      <p>&copy; 2024 TravelGo. Todos los derechos reservados.</p>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: #2c3e50;
  color: white;
  padding: 3rem 2rem 1rem;
}

.footer-container {
  max-width: 1200px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  margin-bottom: 2rem;
}

.footer-section h4 {
  margin-bottom: 1rem;
  font-size: 18px;
  color: #1abc9c;
}

.footer-section p {
  line-height: 1.6;
  color: #bbb;
  font-size: 14px;
}

.footer-section ul {
  list-style: none;
  padding: 0;
}

.footer-section ul li {
  margin-bottom: 0.5rem;
}

.footer-section a {
  color: #bbb;
  text-decoration: none;
  transition: color 0.3s ease;
  font-size: 14px;
}

.footer-section a:hover {
  color: #1abc9c;
}

.social-links {
  display: flex;
  gap: 1rem;
}

.social-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  background: rgba(26, 188, 156, 0.1);
  border-radius: 50%;
  transition: all 0.3s ease;
}

.social-icon:hover {
  background: #1abc9c;
}

.social-icon i {
  font-size: 20px;
}

.footer-bottom {
  text-align: center;
  padding-top: 2rem;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  color: #999;
  font-size: 14px;
}

@media (max-width: 768px) {
  .footer-container {
    grid-template-columns: 1fr;
  }
}
</style>
