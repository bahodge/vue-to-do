<template>
  <div>
    <h1 class="header">Todo List</h1>
  </div>
</template>

<script>
const styleHelper = {
  color: "white",
  margin: 0,
  padding: "2rem",
  backgroundColor: "grey"
};

export default {
  name: "Header",
  created() {
    styleHelper;
  }
};
</script>

<style>
.header {
  color: white;
  margin: 0;
  padding: 2rem;
  background-color: grey;
}
</style>
