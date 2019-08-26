<template>
  <button :type="type">Add task</button>
</template>

<script>
export default {
  props: ['type'],

  name: 'AddTaskButton',

  data () {
    return {

    }
  }
}
</script>

<style lang="css" scoped>
</style>
