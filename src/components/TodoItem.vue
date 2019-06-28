<template>
  <li
    v-on:click="markComplete(todo)"
    class="todo"
    :style="handleComponentStyles(todo)"
  >{{todo.title}}</li>
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
    handleComponentStyles
  }
};
</script>

<style scoped>
li {
  background-color: whitesmoke;
  margin: 0 auto;
  padding: 15px;
}

.incomplete {
  color: orange;
}

.completed {
  color: green;
}
</style>
