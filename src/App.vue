<template>
  <div id="app"></div>
  <todo-app> </todo-app>
</template>

<script>
import TodoApp from './components/TodoApp.vue';

export default {
  name: 'App',
  components: {
    TodoApp
  },
};
</script>
