<template>
  <Header />
  <Hero />
  <Projects />
  <About />
  <Footer />
</template>

<script setup>
    import Header from './components/Header.vue';
    import Hero from './components/Hero.vue';
    import Projects from './components/Projects.vue';
    import About from './components/About.vue';
    import Footer from './components/Footer.vue';
</script>

<style scoped>
.app {
  display: grid;
  grid-template-rows: auto 1fr auto;
  align-items: start;
  min-height: 100vh;
  width: 80rem; /* Define el ancho en rem */
  max-width: 80%; /* Se adapta dinámicamente */
  margin: 0 auto; /* Centra el contenido */
  background-color: #0962bb;
}

</style>
