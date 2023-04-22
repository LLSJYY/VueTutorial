<template>
  <input type="text" v-model="modelValue" @input="handlerInput" />
  <button @click="addTodo">aa</button>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      <input type="checkbox" v-model="todo.completed" @click="(e) => handlerCheck(e, todo)" />
      {{ todo !== undefined ? todo.power : 'add' }}
      <button @click="removeTodo(todo)">remove</button>
    </li>
  </ul>
</template>

<script lang="ts">
type Todo = {
  modelValue: string
  todos: ITodos[]
}

interface ITodos {
  id: number
  power: string
  completed: boolean
}

let id = 0
export default {
  name: 'Todo',
  data(): Todo {
    return {
      modelValue: 'S', // modelvalue 에는 's' ,
      todos: []
    }
  },
  methods: {
    handlerInput() {
      console.log(this.modelValue) //속상하네..
    },
    addTodo() {
      this.todos.push({ id: id++, power: this.modelValue, completed: false })
    },
    removeTodo(todo: any) {
      this.todos = this.todos.filter((target) => target.id !== todo.id)
    },
    handlerCheck(e, todo) {
      this.todos = this.todos.map((target) =>
        target.id === todo.id ? { ...target, completed: !target.completed } : target
      )

      console.log(this.todos)
    }
  }
}
</script>
