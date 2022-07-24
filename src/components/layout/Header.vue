<template>
  <header class="header">
    <h1>TodoList</h1>
    <div id="nav">
      <router-link to="/">Home</router-link> 
      <router-link to="/about">About</router-link>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header-page"
}
</script>

<style scoped>
  .header {
    background-color: rgb(82, 82, 226);
    color: #fff;
    text-align: center;
    padding: 10px 40px;
    display: flex;
    justify-content: space-between;
    align-items: center;

  }

  .header a {
    color: #fff;
    padding-left: 20px;
    text-decoration: none;
  }
</style>


