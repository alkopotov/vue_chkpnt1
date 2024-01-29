<template>
  <main>
   <ToDoItem
    v-for="todo in todos"
    :key="todo.id"
    :todo="todo"
    @change="changeItem"
    @remove="removeItem"
  >
  </ToDoItem>
 
  </main>

</template>


<script>
  import ToDoItem from './TodoItem.vue';
  export default {
    components: {
      ToDoItem,
    },
    props: ['todos'],
    emits: ['change', 'remove'],
    methods: {
      changeItem(id) {
        this.$emit('change', id)
      },
      removeItem(id) {
        this.$emit('remove', id)
      }
    }
  }
 

</script>


<style>
  .todo_item{
    display: flex;
    flex-direction: column;

    margin: 20px 170px;
    padding: 10px;

    outline: 2px solid black;
    box-shadow: 5px 5px 5px black;
}


.input_elem{
    display: flex;
    justify-content: center;
    margin: 20px 400px;
}

.input_elem > input{
    width: 100%;
    box-shadow: 5px 5px 5px black;
}

</style>