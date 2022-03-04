<template>
  <div class="add_todo_container">
    <!-- input and add button -->
    <div style="display: flex">
      <input
        v-model="newTodo"
        class="input"
        type="text"
        placeholder="Add New Task"
        @keypress.enter="addTodo"
      />

      <!-- button -->
      <button class="addTodoBtn" @click="addTodo">Add Todo</button>
    </div>

    <p v-for="todo in todos" :key="todo.id">
      {{ todo.todo }}
      <button class="cancelTodoBtn" @click="cancelTodo(todo.id)">
        Cancel Todo
      </button>
    </p>
  </div>
</template>

<script>
let id = 0;
export default {
  data() {
    return {
      newTodo: "",
      todos: [
        { id: id++, todo: "Make a todo app using Vue.js" },
        {
          id: id++,
          todo: "Continue Node.js course that you've purchased on Udemy",
          completed: false,
        },
      ],
    };
  },
  methods: {
    addTodo() {
      this.newTodo === ""
        ? alert("Add a task!")
        : this.todos.push({ id: id++, todo: this.newTodo });
      this.newTodo = "";
    },
    cancelTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
  },
};
</script>

<style>
.add_todo_container {
  display: flex;
  align-items: center;
  flex-direction: column;
  margin-top: 1rem;
}

.input {
  border-radius: 5px;
  width: 20rem;
  padding: 5px;
  text-align: center;
  margin-right: 3px;
}

.addTodoBtn {
  border-radius: 5px;
}

.addTodoBtn:hover {
  background-color: rebeccapurple;
  transition: 0.3s;
  color: white;
}

.cancelTodoBtn {
  border-radius: 5px;
}

.cancelTodoBtn:hover {
  background-color: rgb(201, 30, 44);
  transition: 0.3s;
  color: white;
}
</style>
