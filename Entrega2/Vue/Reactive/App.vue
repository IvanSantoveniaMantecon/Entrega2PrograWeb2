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
import { reactive } from 'vue';
import Greeting from './components/Greeting.vue';
import LanguageSelector from './components/LanguageSelector.vue';

export default {
  components: {
    Greeting,
    LanguageSelector
  },
  setup() {
    // Objeto reactivo para almacenar el estado de la aplicación
    const state = reactive({
      name: '',
      selectedLanguage: 'es'
    });

    return {
      state
    };
  }
};
</script>
