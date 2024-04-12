<script>
  import { writable } from 'svelte/store';

  // Creamos una lista de tareas reactiva
  const tasks = writable([]);

  // Función para agregar una nueva tarea
  function addTask(task) {
    tasks.update(existingTasks => [...existingTasks, { id: Date.now(), text: task, completed: false }]);
  }

  // Función para eliminar una tarea
  function deleteTask(id) {
    tasks.update(existingTasks => existingTasks.filter(task => task.id !== id));
  }

  // Función para marcar una tarea como completada
  function toggleCompleted(id) {
    tasks.update(existingTasks => existingTasks.map(task => {
      if (task.id === id) {
        return { ...task, completed: !task.completed };
      }
      return task;
    }));
  }
</script>

<h1>Lista de Tareas</h1>

<!-- Componente para agregar nuevas tareas -->
<AddTask on:addTask={addTask} />

<!-- Componente para mostrar la lista de tareas -->
<TaskList bind:tasks={tasks} on:deleteTask={deleteTask} on:toggleCompleted={toggleCompleted} />

<style>
  h1 {
    text-align: center;
  }
</style>
