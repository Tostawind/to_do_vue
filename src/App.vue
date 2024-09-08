<script setup>
import { ref } from 'vue';
import Task from './components/Task.vue';

let id = 0;
const tasks = ref([
  { id: id++, text: 'Tarea 1', isDone: false },
  { id: id++, text: 'Tarea 2', isDone: true },
  { id: id++, text: 'Tarea 3', isDone: false },
]);

const inputValue = ref('');

const addTask = () => {
  tasks.value.push({
    id: id++,
    text: inputValue.value,
    isDone: false,
  });

  inputValue.value = '';
};
</script>

<template>
  <main>
    <ul class="tasks">
      <Task v-for="task of tasks" :key="task.id" :task="task" />
    </ul>
  </main>
  <footer class="footer">
    <input type="text" class="footer__input" v-model="inputValue" />
    <button v-on:click="addTask" class="footer__btn">Añadir</button>
  </footer>
</template>

<style scoped>
main {
  height: 60vh;
}

.tasks {
  list-style: none;
  width: 100%;
}

.footer {
  display: flex;
  gap: 10px;
}

.footer__input {
  padding: 10px;
  border: 1px solid #22222240;
  border-radius: 4px;
}
</style>
