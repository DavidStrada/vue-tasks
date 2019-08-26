<template>
  <div>
    <template v-if="tasks.length">
      <task
        v-on:task:toggleDone="toggleDone"
        v-on:task:deleted="deleteTask"
        v-for="task in tasks" :task="task" :key="task.id"
      ></task>
    </template>

    <span v-else>
      <p>No tasks</p>
    </span>
    <br>

    <task-form v-on:task:added="addTask"></task-form>

  </div>
</template>

<script>

import Task from './Task'
import TaskForm from './TaskForm'

export default {
  components: {
    Task,
    TaskForm
  },

  name: 'Tasks',

  data () {
    return {
      tasks: []
    }
  },
  methods: {
    addTask (task) {
      this.tasks.push(task)
    },
    toggleDone (taskId) {
      let task = this.tasks.find(task => task.id === taskId)
      task.done = !task.done
    },
    deleteTask (taskId) {
      let taskIndex = this.tasks.findIndex(task => task.id === taskId)
      this.tasks.splice(taskIndex, 1)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
