<script setup>
defineProps({
  task: { id: Number, text: String, isDone: Boolean },
});
</script>

<template>
  <li class="task">
    <div class="task__text">{{ task.text }}</div>
    <input type="checkbox" v-model="task.isDone" />
  </li>
</template>

<style scoped>
.task {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  padding: 10px 20px;
  border: 1px solid;
  margin-bottom: 10px;
}

.task__text {
  width: 200px;
  text-align: left;
}
</style>
