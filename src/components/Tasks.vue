<template>
  <div>
    <div v-for="(task, index) in tasks" :key="index">
      <Task
        @toggle-reminder="$emit('toggle-reminder', task.id)"
        @delete-task="$emit('delete-task', task.id)"
        :task="task"
      />
    </div>
  </div>
</template>

<script>
import Task from "./Task.vue";
export default {
  name: "Tasks",
  components: {
    Task
  },
  props: {
    tasks: Array
  },
 emits: ['delete-task', 'toggle-reminder'],
};
</script>

<style>
</style>