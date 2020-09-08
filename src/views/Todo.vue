<template>
  <div class="container">
    <div class="row mt-4">
    <div class="col-12">
      <div class="card text-left">
      <div class="card-header text-center"><b>My Todos</b></div>
        <div class="card-body">
        <Todos v-bind:todos="todos"  v-on:del-todo="deleteTodo" />
        </div>
      </div>
    </div>      
    </div>
  </div>

</template>


<script>
import Todos from '../components/Todos';
import axios from 'axios';

export default {
  name: 'Todo',
  components: {
    Todos,
  },
  data(){
    return {
      todos:[]
    }
  },
  methods:{
    deleteTodo(id){
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
      .then(this.todos = this.todos.filter(todo => todo.id !== id))
      .catch(err => console.log(err));
    },

    addTodo(newTodo){
      const { title, completed } = newTodo;

      axios.post('https://jsonplaceholder.typicode.com/todos', {
        title,
        completed
      })
      .then(res => this.todos = [...this.todos, res.data])
      .catch(err => console.log(err));
    }
  },

  created(){
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=15')
    .then(res => this.todos = res.data)
    .catch(err => console.log(err));

  }
}
</script>