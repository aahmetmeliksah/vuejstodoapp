<template>
  <Header />
  <AddTodo />
</template>

<script>
import Header from "./components/HeaderComp.vue";
import AddTodo from "./components/AddTodoComp.vue";

export default {
  components: {
    Header,
    AddTodo,
  },
};
</script>

<style>
* {
  font-family: sans-serif;
}
</style>
