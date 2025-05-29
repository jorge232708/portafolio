<template>
  <section class="hero">
    <div class="hero-content">
      <div class="text-content">
        <h1>{{ title }}</h1>
        <p>{{ description }}</p>
        <button @click="handleAction">{{ buttonText }}</button>
      </div>
      <img class="avatar" :src="avatarSrc" :alt="altText" />
    </div>
  </section>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  avatarSrc: {
    type: String,
    default: '/Avatar.png' // Ruta en public/
  },
  altText: {
    type: String,
    default: 'Foto de perfil'
  },
  title: {
    type: String,
    default: 'Hola, soy Jorge, pero me dicen Joaco.'
  },
  description: {
    type: String,
    default: 'Soy un desarrollador frontend con una profunda pasión por Vue.js y el diseño minimalista. Me especializo en la creación de interfaces limpias, intuitivas y altamente funcionales, priorizando la modularidad y el rendimiento. Cada línea de código que escribo está pensada para ofrecer una experiencia de usuario fluida y atractiva, combinando la potencia de Vue.js con las mejores prácticas en CSS y JavaScript. Mi enfoque minimalista no solo busca estética, sino también claridad y eficiencia en la estructura del código, asegurando que los proyectos sean escalables y fáciles de mantener.'
  },
  buttonText: {
    type: String,
    default: 'Ver proyectos'
  },
  actionLink: {
    type: String,
    default: '/projects'
  }
});

const handleAction = () => {
  window.location.href = props.actionLink;
};
</script>

<style scoped>
.hero {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 80vh;
  padding: 2rem;
  background-color: #0044aa;
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr auto; /* Texto a la izquierda, imagen a la derecha */
  align-items: center;
  width: 85%;
  max-width: 1100px;
  gap: 30px;
  color: #fff;
}

.text-content {
  display: flex;
  flex-direction: column;
  justify-content: center; /* Centra verticalmente */
  align-items: center; /* Centra horizontalmente */
  text-align: justify;
}

h1 {
  font-size: 1.8rem;
  margin-top: 5rem;
  margin-bottom: 2.5rem;
  text-align: center;
}

p {
  font-size: 1rem;
  margin-bottom: 3rem;
}

button {
  background-color: #ffffff;
  color: #000;
  padding: 1rem 2.5rem; /* Botón más largo */
  font-size: 1.2rem;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  transition: background-color 0.3s;
  margin-top: 1.5rem; /* Espaciado para que no esté pegado al texto */
}

button:hover {
  background-color: #ddd;
}

.avatar {
    margin-top: 3rem;
  width: 400px;
  height: 400px;
  border-radius: 50%;
  object-fit: cover;
  margin-left: 3rem; /* Espacio entre la imagen y el texto */
}
</style>
