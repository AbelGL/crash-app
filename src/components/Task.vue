<template>
  <div
    @dblclick="$emit('toggle-reminder', task.id)"
    :class="[task.reminder ? 'reminder' : '', 'task']"
  >
    <h3>
      {{task.text}}
      <i @click="$emit('delete-task', task.id)" class="fas fa-times"></i>
    </h3>
    <p>{{task.day}}</p>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: Object
  }
};
</script>

<style scoped>
.fas {
  color: rgb(199, 25, 25);
  position: absolute;
  z-index: 999;
  right: 15px;
}
.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
  position: relative;
}
.task.reminder {
  border-left: 5px solid green;
}

.task.reminder h3,
.task.reminder p {
  text-decoration: line-through;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>