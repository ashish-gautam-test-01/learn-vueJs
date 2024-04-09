<script setup>
import { ref } from 'vue'

// give each todo a unique id
let id = 0

const todos = ref([])
const newTodo = ref("")

function addTodo() {
  if(newTodo && newTodo != ""){
    let tempVal = {
      id: id++,
      text: newTodo.value
    }
  	todos.value.push(tempVal)
    newTodo.value = ''
  }else{
    alert("empty data not accepted!")
  }
}

  console.log("todos : ",todos)
function removeTodo(todoId) {
  todos.value = todos.value.filter((item) => item.id != todoId )
}
</script>

<template>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo" required placeholder="Add todo title">
    <button>Add Todo</button>
  </form>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{ todo.text }}
      <button @click="removeTodo(todo.id)">X</button>
    </li>
  </ul>
</template>