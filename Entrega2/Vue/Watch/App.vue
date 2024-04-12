<template>
  <div>
    <h1>Saludo Personalizado</h1>
    <!-- Componente del selector de idioma -->
    <LanguageSelector />
    <!-- Componente del saludo personalizado -->
    <Greeting />
  </div>
</template>

<script>
import { ref, reactive, watch } from 'vue';
import Greeting from './components/Greeting.vue';
import LanguageSelector from './components/LanguageSelector.vue';

export default {
  components: {
    Greeting,
    LanguageSelector
  },
  setup() {
    // Variable reactiva para almacenar el nombre
    const name = ref('');
    
    // Objeto reactivo para almacenar el estado de la aplicación
    const state = reactive({
      selectedLanguage: 'es'
    });

    // Variable reactiva para almacenar el saludo
    const greeting = ref('¡Bienvenido!');

    // Observa cambios en el nombre y el idioma seleccionado
    watch([name, () => state.selectedLanguage], ([newName]) => {
      switch (state.selectedLanguage) {
        case 'es':
          greeting.value = `¡Hola, ${newName}!`;
          break;
        case 'en':
          greeting.value = `Hello, ${newName}!`;
          break;
        case 'fr':
          greeting.value = `Bonjour, ${newName}!`;
          break;
        default:
          greeting.value = `¡Hola, ${newName}!`;
      }
    });

    return {
      name,
      state,
      greeting
    };
  }
};
</script>
