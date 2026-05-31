# 📽️ GUIÓN DE PRESENTACIÓN - LANDING PAGE VUE

## 🎯 ESTRUCTURA DE LA PRESENTACIÓN

---

## 1️⃣ CREACIÓN DEL PROYECTO

### Qué decir:
"Este es un proyecto de landing page desarrollado con Vue 3. Lo creé utilizando Vite como herramienta de construcción, que es un empaquetador moderno y rápido. 

Para crear el proyecto, utilicé el comando:
```
npm create vite@latest landing-page-vue -- --template vue
```

Luego instalé las dependencias necesarias con `npm install`. El proyecto está completamente funcional y listo para producción."

**Mostrar:** La carpeta del proyecto en el explorador de archivos.

---

## 2️⃣ EXPLICACIÓN DE LA TECNOLOGÍA (Vue)

### Qué decir:
"Vue es un framework JavaScript progresivo para construir interfaces de usuario. 

**Ventajas principales:**
- ✅ **Fácil de aprender**: Tiene una curva de aprendizaje más suave que React, especialmente para principiantes
- ✅ **Componentes reactivos**: Vue utiliza un sistema de reactividad automática que es muy intuitivo
- ✅ **Archivos .vue**: Cada componente es un archivo único que contiene HTML, JavaScript y CSS, todo en un solo lugar
- ✅ **Documentación excelente**: La documentación oficial de Vue es muy clara y completa
- ✅ **Rendimiento optimizado**: Vue es muy rápido y eficiente en términos de renderizado

**Entorno utilizado:**
- Vue 3 (versión más reciente)
- Vite (empaquetador ultrarrápido)
- Node.js para gestionar dependencias
- npm como gestor de paquetes

Vue es ideal para proyectos medianos y pequeños, y es especialmente bueno si valoras la claridad y la organización del código."

---

## 3️⃣ EXPLICACIÓN BREVE DE LA ESTRUCTURA

### Qué decir:
"La estructura del proyecto está organizada de la siguiente manera:

```
landing-page-vue/
├── src/
│   ├── components/          ← Componentes reutilizables
│   │   ├── Navigation.vue   (Navbar con menú responsive)
│   │   ├── Footer.vue       (Pie de página)
│   │   ├── Card.vue         (Tarjetas de destinos)
│   │   ├── Button.vue       (Botones reutilizables)
│   │   ├── Icon.vue         (Iconos)
│   │   ├── Modal.vue        (Modal de éxito)
│   │   └── ContactForm.vue  (Formulario de contacto)
│   ├── layouts/
│   │   └── MainLayout.vue   (Envuelve Navigation + Content + Footer)
│   ├── pages/
│   │   └── Home.vue         (Página principal)
│   ├── assets/              (Imágenes)
│   ├── App.vue              (Componente raíz)
│   └── main.js              (Punto de entrada)
├── index.html
└── package.json
```

**Patrón utilizado:**
- Cada componente es un archivo `.vue` que contiene:
  - `<script setup>` para la lógica (es la forma moderna de Vue)
  - `<template>` para el HTML
  - `<style scoped>` para estilos específicos del componente

**Ventaja:** El código es muy legible porque toda la lógica, HTML y estilos de un componente están en un único archivo."

---

## 4️⃣ EJECUCIÓN DEL PROYECTO EN ENTORNO LOCAL

### Qué decir:
"Ahora voy a mostrarles cómo ejecutar el proyecto en el entorno local.

Abierto el terminal en la carpeta del proyecto, ejecuto el comando:
```
npm run dev
```

Este comando inicia el servidor de desarrollo de Vite. El servidor está escuchando en `http://localhost:5177`"

**Mostrar:** 
- Abrir terminal
- Ejecutar `npm run dev`
- Mostrar el mensaje de éxito
- Abrir el navegador en `localhost:5177`

**Qué decir después:**
"Como ven, el proyecto está corriendo localmente. El servidor de desarrollo recompila automáticamente los cambios en tiempo real (hot module replacement), lo que hace que el desarrollo sea muy fluido."

---

## 5️⃣ FUNCIONAMIENTO Y ESTRUCTURA DE LA LANDING PAGE

### Qué decir:
"La landing page está dividida en varias secciones:

**1. Navegación:**
- Navbar responsive con menú hamburguesa
- Logo de TravelGo
- Enlaces que navegan a diferentes secciones
- En móvil, el menú se colapsa en un hamburguesa

**2. Sección Hero:**
- Imagen de fondo impactante
- Título principal: 'Descubre el Mundo con TravelGo'
- Subtítulo atractivo
- Botón 'Contáctenos' que lleva al formulario

**3. Sección Servicios:**
- Grid de 4 tarjetas
- Cada tarjeta tiene un ícono, título y descripción
- Los servicios son: Vuelos, Hotel, Alquiler de Autos, Tours Guiados
- Efecto hover que levanta la tarjeta

**4. Sección Destinos:**
- Grid de 6 tarjetas con destinos turísticos
- Cada Card muestra: imagen, título, descripción, precio y rating
- Diseño limpio y profesional

**5. Sección Contacto:**
- Formulario completo con validaciones
- Se verá en detalle en la siguiente sección

**6. Footer:**
- Información de la empresa
- Enlaces rápidos
- Redes sociales (Facebook, Twitter, Instagram)
- Copyright

**Responsive:**
Todo está diseñado para funcionar en dispositivos móviles, tablets y desktop. Vean cómo al reducir la pantalla, el diseño se adapta automáticamente."

**Mostrar:** Ir scrolleando por cada sección y mostrar el hover effects.

---

## 6️⃣ FUNCIONAMIENTO DEL FORMULARIO

### Qué decir:
"El formulario tiene validaciones en tiempo real. Veamos cómo funciona:

**Campos del formulario:**
1. Nombre Completo
2. Correo Electrónico
3. Teléfono
4. Destino Preferido (select)
5. Mensaje

**Validaciones:**
- Mientras escribo en los campos, aparecen mensajes de error en rojo si hay algo incorrecto
- Nombre: Mínimo 3 caracteres
- Email: Debe tener formato válido (@)
- Teléfono: Solo números, +, -, espacios y paréntesis
- Destino: Debe seleccionar uno
- Mensaje: Mínimo 10 caracteres

**Botón Enviar:**
- Se desactiva automáticamente si hay errores
- Solo se activa cuando TODOS los campos son válidos

**Modal de Éxito:**
- Cuando envío el formulario correctamente, aparece un modal elegante
- Muestra un mensaje de confirmación personalizado
- Es un componente reutilizable que podría usarse en otros formularios"

**Mostrar:** 
- Escribir datos incorrectos y ver los mensajes de error aparecer
- Ver el botón desactivado
- Escribir correctamente y ver el botón habilitarse
- Enviar el formulario y mostrar el modal

---

## 7️⃣ DESPLIEGUE DEL PROYECTO

### Qué decir:
"Para desplegar este proyecto, utilicé [SERVICIO DE DESPLIEGUE: Vercel / Netlify / GitHub Pages / Render / etc].

**Pasos que realicé:**

1. **Repositorio GitHub:**
   - Subí el proyecto a un repositorio en GitHub
   - La estructura está bien organizada
   - Incluye .gitignore para excluir node_modules

2. **Conexión con la plataforma de despliegue:**
   - Conecté el repositorio con [PLATAFORMA]
   - Configuré los ajustes de build
   - Comando de build: `npm run build`
   - Carpeta de salida: `dist`

3. **Despliegue automático:**
   - Cada vez que hago push a la rama main, se despliega automáticamente
   - No requiere configuración manual cada vez

4. **URL pública:**
   - El proyecto está disponible en: [INSERTAR URL DESPLEGADA]
   - Funciona en cualquier navegador y dispositivo"

**Mostrar:** El proyecto desplegado en el navegador.

---

## 8️⃣ VISUALIZACIÓN DEL SISTEMA YA DESPLEGADO

### Qué decir:
"Aquí está el proyecto en vivo. Como ven:

- ✅ La navegación funciona correctamente
- ✅ Todas las secciones cargan sin problemas
- ✅ El responsive design funciona (mostrar en móvil)
- ✅ El formulario está completamente funcional
- ✅ Las validaciones funcionan en tiempo real
- ✅ El modal de éxito aparece al enviar
- ✅ El rendimiento es excelente (carga rápido)

El proyecto está 100% funcional y listo para usar."

**Mostrar:**
- Navegar por todas las secciones
- Probar el formulario
- Mostrar responsive en móvil
- Mostrar velocidad de carga

---

## 🚀 ESTRUCTURA TÉCNICA DE COMPONENTES

### Para ampliar en la evaluación técnica:

**Card.vue:**
"Este componente recibe props (datos) como imagen, título, descripción, precio y rating. Muestra una tarjeta hermosa con efecto hover. Es reutilizable para cualquier tarjeta similar."

**Button.vue:**
"Componente flexible que acepta variantes (primary, secondary) y tamaños (small, medium, large). Esto significa que en lugar de copiar-pegar código de botones, simplemente reutilizo este componente."

**ContactForm.vue:**
"Es un componente que encapsula toda la lógica del formulario: estado, validaciones y modal. Está completamente separado de la página Home, lo que hace el código más limpio y mantenible."

**Reactividad en Vue:**
"En Vue, cuando cambio los datos con `v-model`, la interfaz se actualiza automáticamente. Por ejemplo, cuando escribo en el input, Vue detecta el cambio y ejecuta las validaciones instantáneamente."

---

## 📊 RESUMEN

✅ Proyecto Vue creado con Vite
✅ Componentes bien organizados
✅ Landing page completa con formulario
✅ Validaciones en tiempo real
✅ Diseño responsive
✅ Desplegado en [PLATAFORMA]
✅ Funcional al 100%

---

## 🎓 NOTAS PARA LA EVALUACIÓN

- Explica con naturalidad, sin leer diapositivas
- Muestra casos de uso real (error handling, validaciones)
- Sé capaz de explicar por qué usaste Vue en lugar de otra tecnología
- Ten claro qué es un componente y por qué reutilizar código es importante
- Entiende la estructura de carpetas y por qué está organizada así
