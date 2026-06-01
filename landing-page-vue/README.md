# 🌍 Landing Page - TravelGo con Vue

Una landing page moderna y responsive desarrollada con **Vue 3** y **Vite**, siguiendo una arquitectura escalable con componentes reutilizables. Mismo diseño e implementación que la versión React.

## 📋 Objetivo de la Actividad

Desarrollar una landing page funcional utilizando Vue que incluya:
- ✅ Diseño visual organizado y responsive
- ✅ Componentes reutilizables
- ✅ Formulario funcional con validaciones en frontend
- ✅ Navegación clara y estructura bien definida
- ✅ Design System documentado
- ✅ Despliegue público del proyecto
- ✅ Repositorio en GitHub organizado

## 📁 Estructura del Proyecto

```
src/
├── components/              # Componentes reutilizables
│   ├── Button.vue           # Botones con variantes
│   ├── Card.vue             # Tarjetas de destinos
│   ├── Icon.vue             # Iconos Font Awesome
│   ├── Modal.vue            # Modal popup
│   ├── Navigation.vue       # Barra de navegación
│   ├── ContactForm.vue      # Formulario de contacto
│   └── Footer.vue           # Pie de página
├── pages/                   # Vistas completas
│   ├── Home.vue             # Página de inicio
│   └── DesignSystem.vue     # Documentación del DS
├── layouts/                 # Plantillas de página
│   └── MainLayout.vue       # Layout principal
├── global.css               # Estilos globales
├── style.css                # Estilos base
├── App.vue                  # Componente raíz
└── main.js
```

## 🎨 Componentes Desarrollados

### 1. Button
Componente de botón reutilizable con múltiples variantes.

**Variantes disponibles:**
- `primary` - Botón principal (turquesa)

**Tamaños:**
- `small` - 8px 16px
- `medium` - 12px 24px (por defecto)
- `large` - 16px 32px

**Estados:**
- Normal, Hover, Disabled

```vue
<Button variant="primary" size="large" @click="handleClick">
  Explorar
</Button>
```

### 2. Card
Componente para mostrar destinos/servicios.

**Props:**
- `image`: URL de la imagen
- `title`: Título
- `description`: Descripción
- `price`: Precio (opcional)
- `rating`: Calificación (opcional)

### 3. Icon
Componente de iconos reutilizable usando Font Awesome.

**Tipos disponibles:**
- `flights` - fa-plane-departure
- `hotel` - fa-hotel
- `car` - fa-car
- `compass` - fa-compass

**Tamaños:** small, medium, large

### 4. Modal
Componente modal para alertas y confirmaciones.

**Props:**
- `isOpen`: Control de visibilidad
- `title`: Título
- `message`: Mensaje
- `type`: success | error

**Events:**
- `@close`: Al cerrar el modal

### 5. Navigation
Barra de navegación responsive.

**Características:**
- Links simples (scroll a secciones)
- Design System link (navega a otro componente)
- Menú hamburguesa en mobile
- Estilos activos

**Events:**
- `@navigate`: Emite evento de navegación

### 6. ContactForm
Formulario de contacto con validaciones.

**Validaciones:**
- ✅ Campos requeridos
- ✅ Validación de email
- ✅ Mensajes de error claros
- ✅ Feedback visual

## ✨ Características Principales

### Navegación
- **Links Simples:** Inicio, Destinos, Servicios, Contacto (scroll)
- **Design System:** Enlace especial que navega al componente
- **Menu Responsive:** Hamburguesa en pantallas < 768px

### Home Page
- Hero section atractivo
- Sección de servicios
- Grid de destinos con cards
- Formulario de contacto
- Footer

### Design System
Página dedicada que documenta y muestra:
- **Paleta de colores** - Turquesa, Amarillo, Oscuro, Claro
- **Tipografía** - Headings (h1-h3) y body text
- **Espaciado** - Sistema de espaciado (8-60px)
- **Botones** - Variantes y tamaños
- **Tarjetas** - Ejemplos de cards
- **Iconos** - Todos los tipos disponibles
- **Modal** - Demostración interactiva
- **Formulario** - Ejemplo funcional

## 📱 Responsive Design

El proyecto es completamente responsive:

| Dispositivo | Ancho | Características |
|-------------|-------|-----------------|
| Mobile | < 768px | 1 columna, hamburguesa |
| Tablet | 768px - 1024px | 2 columnas |
| Desktop | > 1024px | 3+ columnas |

## 🎨 Paleta de Colores

| Color | Valor | Uso |
|-------|-------|-----|
| Primary | #1abc9c | Botones, links, accents |
| Accent | #ffc107 | Highlights, calls to action |
| Dark | #1a1a1a | Texto principal |
| Light | #f9f9f9 | Fondos |

## 🛠️ Instalación y Uso

### Requisitos
- Node.js v16 o superior
- npm o yarn

### Pasos

```bash
# 1. Clonar repositorio
git clone https://github.com/usuario/landing-page-vue.git

# 2. Navegar al proyecto
cd landing-page-vue

# 3. Instalar dependencias
npm install

# 4. Iniciar servidor de desarrollo
npm run dev
# Disponible en http://localhost:5173

# 5. Build para producción
npm run build

# 6. Previsualizar build
npm run preview
```

## 📚 Conceptos Implementados

### Vue 3 Composition API
- `ref()` - Estados reactivos
- `computed()` - Propiedades computadas
- `onMounted()` - Ciclo de vida

### Single File Components
- `<script setup>` - Sintaxis moderna
- `<template>` - Templates reactivos
- `<style scoped>` - CSS modular

### Comunicación entre componentes
- Props - De padre a hijo
- Emits - De hijo a padre
- Provide/Inject - Para contexto

## 🚀 Despliegue

### Opciones de despliegue:
- **Vercel** (recomendado)
- **Netlify**
- **GitHub Pages**
- **Firebase Hosting**

### Con Vercel:
```bash
npm install -g vercel
vercel
```

## 📝 Validaciones del Formulario

El formulario incluye:
- ✅ Validación de campos requeridos
- ✅ Validación de formato email
- ✅ Mensajes de error descriptivos
- ✅ Confirmación visual de envío
- ✅ Reset de formulario

## 📦 Tecnologías Utilizadas

- **Vue 3** - Librería UI progresiva
- **Vite 8.0.12** - Build tool
- **CSS3** - Estilos (flexbox, grid)
- **Font Awesome 6.4** - Iconos
- **HTML5** - Estructura semántica

## 🎓 Ventajas de Vue

### Facilidad de aprendizaje
- Sintaxis cercana a HTML
- `<script setup>` más limpio que React
- Documentación clara y ejemplos

### Organización
- Single File Components (.vue)
- CSS scoped automático
- Reactividad más simple

### Componentes
- Props y emits intuitivos
- Slots para composición
- Directivas útiles (v-if, v-for, etc)

### Desarrollo
- Hot reload rápido
- DevTools excelentes
- Comunidad amable

## 📋 Checklist de Entrega

- ✅ Landing page funcional y responsive
- ✅ Componentes reutilizables desarrollados
- ✅ Formulario con validaciones
- ✅ Design System documentado
- ✅ Código limpio y organizado
- ✅ Proyecto desplegado
- ✅ Repositorio en GitHub
- ✅ README completo

---

**Proyecto de Landing Page - TravelGo**  
Desarrollado con Vue 3 + Vite | 2026
