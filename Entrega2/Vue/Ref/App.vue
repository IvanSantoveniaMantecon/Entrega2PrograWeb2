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
import { ref } from 'vue';
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

    // Función para actualizar el nombre
    const updateName = (newName) => {
      name.value = newName;
    };

    return {
      name,
      updateName
    };
  }
};
</script>
