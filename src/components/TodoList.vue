<template>
  <div>
    <input v-model="todoText" @keyup.enter="add"/>
    <button type="button" @click="add">ADD</button>
    <ul>
      <TodoItem v-for="(todo, index) in todos" :todo="todo" :key="index" @deleteItem="deleteItem( index )"></TodoItem>
    </ul>
  </div>
</template>

<script>
import TodoItem from './TodoItem'

export default {
  data() {
    return {
      todos: [
        'Do todo list',
        'Do add function',
        'Do remove function'
      ],
      todoText: ''
    }
  },
  components: {
    TodoItem
  },
  methods: {
    add() {
      if ( this.todoText.length > 0 ) {
        this.todos.push( this.todoText );
        this.todoText = '';
      }
    },
    deleteItem( index ) {
      this.todos.splice( index, 1 );
    }
  }
}
</script>

<style scoped>
ul {
  list-style-type: none;
}

input {
  width: 120px;
}
</style>