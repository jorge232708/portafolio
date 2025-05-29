<template>
  <div class="search-menu">
    <input 
      type="text" 
      v-model="query" 
      :placeholder="placeholder"
      @input="handleSearch"
    />
  </div>
</template>

<script setup>
import { ref, defineProps, defineEmits } from 'vue';

const props = defineProps({
  placeholder: {
    type: String,
    default: 'Buscar proyectos...'
  }
});

const emit = defineEmits(['search']);

const query = ref('');

const handleSearch = () => {
  emit('search', query.value); // Envía el texto de búsqueda al padre
};
</script>

<style scoped>
.search-menu {
  display: flex;
  justify-content: center;
  padding: 1rem;
}

input {
  width: 100%;
  max-width: 300px;
  padding: 0.6rem;
  border: none;
  border-radius: 8px;
  font-size: 1rem;
  color: #000;
}
</style>
