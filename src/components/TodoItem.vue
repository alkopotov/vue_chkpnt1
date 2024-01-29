<template>
  <div
    class="todo_item"
    v-bind:style="{backgroundColor: todo.completed ? 'green' : 'red'}"
    @click="changeToDo"
    @dblclick="removeToDo" 
  >
    {{ todo.title }}</div>
</template>


<script>
export default {
  props: ['todo'],
  emits: ['change', 'remove'],
  methods: {
    changeToDo() {
      this.$emit('change', this.todo.id)
    },
    removeToDo() {
      this.$emit('remove', this.todo.id)
    }
  }
}

</script>


<style>


</style>