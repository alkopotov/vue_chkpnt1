<template>
  <div className="input_elem">
      <input 
      @keydown="handler"/>
  </div>
</template>

<script>

export default {
  emits: ['add'],
  methods: {
    addToDo(title) {
      this.$emit('add', title)
    },
    handler(e) {
      if (e.key === 'Enter') {
        this.addToDo(e.target.value)
      }
    }
  }
}


</script>

<style>


</style>