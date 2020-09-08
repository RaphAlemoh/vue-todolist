<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">      
        <ul class="list-group border-0 bg-none">
        <div  class="list-group-item border-0 bg-none">
        <div class="form-check form-check-inline">
        <label class="form-check-label">
        <input class="form-check-input" type="checkbox" v-on:change="markComplete">
             <strong>Title :</strong> {{ todo.title }}  
        <button @click="$emit('del-todo', todo.id)" class="del">X</button>
        </label>
    </div>
        </div>
        </ul>
    </div>
</template>


<script>
export default {
    name: "TodoItem",
    props:["todo"],
    methods:{
        markComplete(){
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>


<style scoped>
.todo-item{
    background: #f4f4f4;
    padding: 10px;
    padding-bottom: 1px #ccc dotted;
}

.is-complete{
    text-decoration:line-through;

}

.del{
    background: #ff0000;
    color: #fff;
    border: none;
    border-radius: 50%;
    cursor: pointer;
    float: right;
}
</style>