<template>
  <div>
    
    {{ fullName }} <br> <br>
    
    <h2>TODOS EM ABERTO</h2> <br>
    
    <div 

      v-for="todo in uncompletedeTodos"
      :key="todo.id"
      >
        {{ todo.title }}
      
    </div>

    <h2>TODOS COMPLETAS</h2>

    <div 

      v-for="todo in completedeTodos"
      :key="todo.id"
      >
        {{ todo.title }}
      
    </div>

    <h2>TODOS</h2>

    <div 

      v-for="todo in todos"
      :key="todo.id"
      >
      <input 
        v-model="todo.completed"
        type="checkbox"
      >
        {{ todo.title }}
      
    </div>

  </div>
</template>

<script>

export default {
  name: 'App',
   
  data() {
    return {
      user: {
        first_name: 'Ricardo',
        last_name: 'Navarro',
      },
      todos: [
  {
    "userId": 1,
    "id": 1,
    "title": "delectus aut autem",
    "completed": false
  },
  {
    "userId": 1,
    "id": 2,
    "title": "quis ut nam facilis et officia qui",
    "completed": false
  },
  {
    "userId": 1,
    "id": 3,
    "title": "fugiat veniam minus",
    "completed": false
  },
  {
    "userId": 1,
    "id": 4,
    "title": "et porro tempora",
    "completed": true
  },
  {
    "userId": 1,
    "id": 5,
    "title": "laboriosam mollitia et enim quasi adipisci quia provident illum",
    "completed": false
  }
]
    }
  },
  computed: {
    fullName() {
      return `${this.user.first_name} ${this.user.last_name}`
    },
    uncompletedeTodos() {
      return this.todos.filter(todo => !todo.completed);
    },
    completedeTodos() {
      return this.todos.filter(todo => todo.completed);
    },
  },
  methods: {
    
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
  margin-left: 60px;
}
</style>
