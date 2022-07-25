<template>
  <div>
    <form @submit.prevent="addTodo">
      <input type="text" v-model="title" name="title" placeholder="Add Todo...">
      <input type="submit" value="Submit" class="btn">
    </form>
  </div>
</template>

<script>
// import uuid from 'uuid';
export default {
  name: "AddTodo",
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addTodo() {
      const newTodo = {
        title: this.title,
        completed: false
      }
      // Send up to parent
      this.$emit('add-todo', newTodo);

      this.title = '';
    }
  }
}
</script>

<style scoped>
  form {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  input[type="text"] {
    padding: 10px;
    width: 50%;
    margin-top: 20px;
    /* border-radius: 10px; */
    border: none;
    border-bottom: 2px solid rgb(82, 82, 226);
  }

  input[type="submit"] {
    /* width: 25%; */
    border-radius: 10px;
    margin-top: 20px;
    background-color: rgb(82, 82, 226);
    padding: 10px;
    min-width: fit-content;
  }

  @media (max-width: 425px) {
    input[type="text"] {
      width: 80%;
    }
  }
</style>


