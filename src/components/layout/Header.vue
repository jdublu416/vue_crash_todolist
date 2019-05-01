<template>
  <header class="header">
    <h1>toDo List</h1>
    <div id="nav">
      <router-link to="/">Home</router-link>|
      <router-link to="/about">About</router-link>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header"
};
</script>

<style scoped>
.header {
  background: #677a90;
  padding: 40px 5px;
  height: 250px;
  color: #fff;
  text-align: center;
  opacity: 0.85;
  font-size: 1.5rem;
}

.header a {
  text-decoration: none;
  color: #fff;
  padding-right: 5px;
  padding-left: 5px;
}
</style>

