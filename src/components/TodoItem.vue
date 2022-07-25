<template>
<div class="all-todos">
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <p>
      <input type="checkbox" v-on:change="markComplete" style="margin-right: 5px;" v-bind:checked="todo.completed">
      {{todo.title}}
      <button @click="$emit('del-todo', todo.id)" class="del">x</button>
      </p>
  </div>
</div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      // eslint-disable-next-line
      this.todo.completed = !this.todo.completed;
    }
  }
}
</script>

<style scoped>
  .all-todos {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 20px 0;
  }

  .todo-item {
    /* background: #f4f4f4; */
    background-color: rgb(225, 225, 255);
    padding: 10px;
    border-bottom: 1px #ccc dotted;
    width: 50%;
    border-radius: 10px;
  }

  .is-complete {
    text-decoration: line-through;
    color: grey;
    background-color: rgb(250, 214, 214);
  }

  .del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
    font-weight: bold;
  }



  @media (max-width: 425px) {
    .todo-item {
      width: 80%;
    }
  }
</style>

