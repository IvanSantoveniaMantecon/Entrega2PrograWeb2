<script>
  import { createEventDispatcher } from 'svelte';

  // Creamos un evento para enviar la nueva tarea al componente padre
  const dispatch = createEventDispatcher();

  // Variable para almacenar el texto de la nueva tarea
  let taskText = '';

  // Función para agregar la nueva tarea y enviarla al componente padre
  function addTask() {
    if (taskText.trim() !== '') {
      dispatch('addTask', taskText.trim());
      taskText = '';
    }
  }
</script>

<div>
  <input type="text" bind:value={taskText} placeholder="Ingrese una nueva tarea">
  <button on:click={addTask}>Agregar Tarea</button>
</div>
