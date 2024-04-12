<script>
  // Prop para recibir la lista de tareas del componente padre
  export let tasks;

  // Eventos personalizados para comunicarse con el componente padre
  export let deleteTask;
  export let toggleCompleted;
</script>

<ul>
  {#each $tasks as task}
    <li>
      <input type="checkbox" bind:checked={task.completed} on:change={() => toggleCompleted(task.id)}>
      <span style="{task.completed ? 'text-decoration: line-through;' : ''}">{task.text}</span>
      <button on:click={() => deleteTask(task.id)}>Eliminar</button>
    </li>
  {/each}
</ul>
