<template>
  <form @submit.prevent="onSubmit(title)">
    <input v-model.trim="title" placeholder="Add todo...">
    <button type="submit">Add</button>
  </form>
</template>

<script>
function onSubmit() {
  if (!this.title) return;

  const newTodo = {
    title: this.title,
    completed: false,
    id: null
  };
  this.$emit("create-todo", newTodo);
  this.title = null;
}

export default {
  name: "AddTodo",
  data() {
    return {
      title: null
    };
  },
  methods: { onSubmit }
};
</script>

<style>
input {
  margin: 0;
  width: 99%;
  padding: 0;
}
button {
  margin: 0;
  width: 99%;
  padding: 0;
}
</style>
