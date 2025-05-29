<template>
  <div class="logo" :class="{ clickable: isClickable }" @click="handleClick">
    <img :src="logoSrc" :alt="altText" />
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';

const props = defineProps({
  logoSrc: {
    type: String,
    default: '/JB.png'
  },
  altText: {
    type: String,
    default: 'Logo'
  },
  isClickable: {
    type: Boolean,
    default: true
  }
});

const emit = defineEmits(['logoClicked']);

const handleClick = () => {
  if (props.isClickable) {
    emit('logoClicked');
  }
};
</script>

<style scoped>
.logo {
  display: flex;
  align-items: center;
  margin-left: 1rem;
}

img {
  width: 60px;
  height: auto;
  cursor: pointer;
  border-radius: 20%;
}
</style>
