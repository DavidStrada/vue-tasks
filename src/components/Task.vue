<template>
  <div class="task" :class="{ 'task--done': task.done}">
   {{  task.body }}
   <a href="#" @click.prevent="toggleDone(task.id)">Mark as {{  task.done ? 'not done' : 'done'}}</a>
   <a href="#" @click.prevent="deleteTask(task.id)">Delete task</a>
  </div>
</template>

<script>
export default {
  props: ['task'],

  name: 'Task',

  data () {
    return {

    }
  },
  methods: {
    toggleDone (taskId) {
      // this.task.done = !this.task.done
      this.$emit('task:toggleDone', taskId)
    },
    deleteTask (taskId) {
      this.$emit('task:deleted', taskId)
    }
  }
}
</script>

<style lang="css" scoped>
.task--done {
  color: green;
  font-weight: 500;
 }
</style>

