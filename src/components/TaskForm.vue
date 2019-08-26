<template>
   <form @submit.prevent="handleSubmit">
    <textarea v-model.trim="task"></textarea>
    <br>
    <add-task-button type="submit"></add-task-button>
  </form>
</template>

<script>
import AddTaskButton from './AddTaskButton'

export default {
  components: {
    AddTaskButton
  },

  name: 'TaskForm',

  data () {
    return {
      task: null
    }
  },
  methods: {
    handleSubmit () {
      if (this.task) {
        this.$emit('task:added', {
          // id: Math.floor(Math.random() * Math.floor(1000)),
          id: Date.now(),
          body: this.task,
          done: false
        })
        this.task = null
      }
    }
  }
}
</script>

<style lang="css" scoped>
</style>
