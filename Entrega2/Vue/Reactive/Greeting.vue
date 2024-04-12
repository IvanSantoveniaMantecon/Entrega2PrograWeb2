<template>
  <p>{{ greeting }}</p>
</template>

<script>
import { computed, inject } from 'vue';

export default {
  setup() {
    // Importamos el objeto reactivo `state` del componente padre
    const state = inject('state');

    // Variable computada para calcular el saludo
    const greeting = computed(() => {
      switch (state.selectedLanguage) {
        case 'es':
          return `¡Hola, ${state.name}!`;
        case 'en':
          return `Hello, ${state.name}!`;
        case 'fr':
          return `Bonjour, ${state.name}!`;
        default:
          return `¡Hola, ${state.name}!`;
      }
    });

    return {
      greeting
    };
  }
};
</script>
