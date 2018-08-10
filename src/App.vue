<template>
  <div id="app">
    <TodoList v-bind:todos="todos" />
    <create-todo v-on:create-todo="createTodo" />
  </div>
</template>

<script>
import sweetalert from 'sweetalert';
import TodoList from './components/TodoList';
import CreateTodo from './components/CreateTodo';

export default {
  name: 'App',
  components: {
    TodoList,
    CreateTodo,
  },
  methods: {
    createTodo(newTodo) {
      console.log('addTodo');
      this.todos.push(newTodo);
      sweetalert('Success', 'Todo created', 'success');
    },
  },
  data() {
    return {
      todos: [{
        title: 'Todo AA',
        projects: 'Project A',
        done: false,
      }, {
        title: 'Todo AB',
        projects: 'Project A',
        done: false,
      }, {
        title: 'Todo AC',
        projects: 'Project A',
        done: false,
      }],
    };
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
