<template>
  <div>
    <form @submit="addTodo">
      <input type="text" v-model='title' name="title" placeholder="Add Todo...">
      <input type="submit" value="Add" class="btn">
    </form>
  </div>
</template>


<script>

import uuid from 'uuid';

export default {
  name: "AddTodo",
  data(){
      return{
      title:''
      }
  },
  methods: {
      addTodo(e){
          e.preventDefault();
            const newTodo = {
                id: uuid.v4(),
                title: this.title,
                completed:false
            }
            this.$emit('add-todo', newTodo);
            this.title = '';
      }
  }
}
</script>

<style scoped>
form {
  display: flex;
  /* margin: 12px 0; */
}
.btn {
  background: #677a90;
  color: #fff;
  padding: 5px;
  border: 1px solid black;
}
input[type="text"] {
  flex: 10;
  padding: 10px;
}
input[type="submit"] {
  flex: 2;
}
</style>
