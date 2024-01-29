<template>
  <AddToDo
    @add="addToDo">
  </AddToDo>
  <TodoList
    :todos="todos"
    @change="changeToDo"
    @remove="removeToDo"
  >
  </TodoList>
</template>



<script>
  import TodoList from './components/TodoList.vue'
  import AddToDo from './components/AddToDo.vue'
  export default {
    components: {
      TodoList, AddToDo
    },
    data() {
      return {
        todos: [
          {id: 1, title: 'Позавтракать', completed: true},
          {id: 2, title: 'Почистить огурцы', completed: false},
          {id: 3, title: 'Помыть кота', completed: true},
        ]
      }
    },
    methods: {
      addToDo(title) {
        this.todos.push({id: Date.now(), title, completed: false})
      },
      changeToDo(id) {
        this.todos = this.todos.map(elem => {
          if (elem.id === id) {
            elem.completed = !elem.completed
            return elem
          } else {
            return elem
          }
        })
      },
      removeToDo(id) {
        this.todos = this.todos.filter(elem => elem.id !== id)
      }
    }

  }
</script>


<style>

</style>
