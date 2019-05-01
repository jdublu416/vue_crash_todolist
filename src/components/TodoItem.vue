<template>
    <div class="todo-item" v-bind:class="{'is-complete': todo.completed}">
        
        <p>
            <input type="checkbox" v-on:change="markComplete">
            {{todo.title}}
            <button @click="$emit('del-todo', todo.id)" 
            class="del">Delete</button>
            
        </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete(){
           this.todo.completed = !this.todo.completed;
        }
    }
}
</script>

<style scoped>
 .todo-item{
background: #f4f4f4;
padding: 15px;
border-bottom:2px #c2c2c2 solid;
opacity: 0.8;
 }

 .is-complete{
     text-decoration: line-through;
 }

 .del{
background: #ff0000;
color: #fff;
border: none;
padding: 10px;
cursor: pointer;
float: right;
 }
</style>
