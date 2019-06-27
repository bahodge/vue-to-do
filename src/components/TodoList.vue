<template>
  <div>
    <h1>Todo List</h1>
    <p v-for="todo in todo" v-bind:key="todo.id">
      <TodoItem/>
    </p>
  </div>
</template>


<script>
import TodoItem from "./TodoItem";
export default {
  name: "Todo",
  data() {
    return {
      todos: [
        { title: "Do Work", id: 1, completed: true },
        { title: "Do More Work", id: 2, completed: false },
        { title: "Do Even more work!", id: 3, completed: false }
      ]
    };
  }
};
</script>


