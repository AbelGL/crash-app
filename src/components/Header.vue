<template>
  <header>
    <h1>{{title}}</h1>
    <Button
      @btn-click="$emit('show-add-task')"
      :text="showAddTask ? 'Close': 'Add Task'"
      :color="showAddTask ? 'red': 'green'"
    />
  </header>
</template>

<script>
import Button from "@/components/Button.vue";
export default {
  name: "Header",
  components: { Button },
  props: {
    title: String,
    showAddTask: Boolean
  }
};
</script>


<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>