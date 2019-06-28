<template>
  <li>
    <span
      v-on:click="markComplete(todo)"
      class="todo"
      :style="handleComponentStyles(todo)"
    >{{todo.title}}</span>
    <span class="delete-btn" @click="deleteTodo(todo)">X</span>
  </li>
</template>

<script>
const styleHelper = {
  orange: "orange",
  green: "green",
  large: "2rem",
  small: "1rem",
  margin: 0
};
const markComplete = todo => (todo.completed = !todo.completed);
const handleComponentStyles = ({ completed }) => {
  const color = completed ? styleHelper.green : styleHelper.orange;
  const fontSize = completed ? styleHelper.small : styleHelper.large;
  return {
    color: color,
    textAlign: "left",
    fontSize: fontSize,
    margin: styleHelper.margin
  };
};

export default {
  name: "TodoItem",
  props: ["todo"],
  create() {
    styleHelper;
  },
  methods: {
    markComplete,
    handleComponentStyles,
    deleteTodo(todo) {
      this.$emit("delete-todo", todo);
    }
  }
};
</script>

<style scoped>
li {
  background-color: whitesmoke;
  margin: 0 auto;
}
.delete-btn {
  text-align: "right";
  font-size: 1rem;
  padding: 1rem;
  float: right;
}
.incomplete {
  color: orange;
}

.completed {
  color: green;
}
</style>
