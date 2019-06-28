<template>
  <div>
    <div>
      <AddTodo @create-todo="createTodo"/>
      <ul>
        <TodoItem
          v-for="todo in todos"
          :key="todo.id"
          v-bind:todo="todo"
          class="todo"
          @delete-todo="deleteTodo"
        />
      </ul>
    </div>
  </div>
</template>


<script>
import TodoItem from "./TodoItem";
import AddTodo from "./AddTodo";

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
  },
  components: {
    TodoItem,
    AddTodo
  },
  methods: {
    handleId() {
      let lastTodo = this.todos[this.todos.length - 1];
      lastTodo ? lastTodo.id + 1 : 1;
    },
    createTodo(todo) {
      todo.id = this.handleId();
      this.todos.push(todo);
    },
    deleteTodo(todo) {
      const existingTodo = this.todos.find(t => t.id == todo.id);
      this.todos = this.todos.filter(todo => todo.id != existingTodo.id);
    }
  }
};
</script>

<style>
ul {
  margin: 0 auto;
  list-style-type: none;
  text-align: left;
  padding: 0;
}

.todo {
  margin: 0.5rem;
  padding: 0.5rem;
  font-size: 2rem;
  cursor: pointer;
}
</style>



