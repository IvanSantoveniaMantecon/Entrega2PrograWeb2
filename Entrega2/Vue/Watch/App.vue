<template>
  <div>
    <h1>Saludo Personalizado</h1>
    <!-- Componente del selector de idioma -->
    <LanguageSelector :state="state" />
    <!-- Componente del saludo personalizado -->
    <Greeting :greeting="greeting" />
  </div>
</template>

<script>
import { ref, watch, computed } from 'vue';
import Greeting from './components/Greeting.vue';
import LanguageSelector from './components/LanguageSelector.vue';

export default {
  components: {
    Greeting,
    LanguageSelector
  },
  setup() {
    // Variable ref para almacenar el estado de la aplicación
    const state = ref({
      name: '',
      selectedLanguage: 'es'
    });

    // Variable computada para calcular el saludo
    const greeting = computed(() => {
      switch (state.value.selectedLanguage) {
        case 'es':
          return `¡Hola, ${state.value.name}!`;
        case 'en':
          return `Hello, ${state.value.name}!`;
        case 'fr':
          return `Bonjour, ${state.value.name}!`;
        default:
          return `¡Hola, ${state.value.name}!`;
      }
    });

    // Vigila los cambios en selectedLanguage y actualiza el saludo
    watch(() => state.value.selectedLanguage, () => {
      greeting.value = computeGreeting();
    });

    // Función para calcular el saludo
    function computeGreeting() {
      switch (state.value.selectedLanguage) {
        case 'es':
          return `¡Hola, ${state.value.name}!`;
        case 'en':
          return `Hello, ${state.value.name}!`;
        case 'fr':
          return `Bonjour, ${state.value.name}!`;
        default:
          return `¡Hola, ${state.value.name}!`;
      }
    }

    return {
      state,
      greeting
    };
  }
};
</script>
