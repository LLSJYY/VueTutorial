<template>
  <v-app>
    <v-navigation-drawer app> </v-navigation-drawer>
    <v-app-bar app> </v-app-bar>
    <v-main>
      <v-container fluid>
        <router-view>
          <ul>
            <li v-for="todo in todos" :key="todo.id">{{ todo.power }}</li>
          </ul>
        </router-view>
      </v-container>
    </v-main>
    <v-footer app> </v-footer>
  </v-app>
</template>

<script lang="ts">
type Todo = {
  todos: ITodos[]
}

interface ITodos {
  id: number
  power: number
}

let id = 0
export default {
  name: 'Todo',
  data(): Todo {
    return {
      todos: [
        { id: id++, power: 10000 },
        { id: id++, power: 9000 },
        { id: id++, power: 7000 },
        { id: id++, power: 8000 }
      ]
    }
  }
}
</script>
