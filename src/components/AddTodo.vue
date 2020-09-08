<template>
<div class="container">
    <div class="row justify-content-center mt-5">
        <div class="col-sm-5 col-md-5 col-lg-5">
            <div class="card shadow-lg border-0 rounded-lg">
              <div class="card-header text-center"><b> Create a Todo</b></div>
                <div class="card-body">
             <form @submit="addTodo">
                    <div class="form-group mb-4">
                        <label for="title">Todo Title</label>
                        <input type="text" v-model="title" name="title" placeholder="add to do" class="form-control form-control-lg" aria-describedby="helpId">
                    </div>                      
                   
                <div class="form-group mb-0">
                        <button type="submit" class="btn btn-success">
                            Add Todo
                        </button>
                </div>
            </form>
                </div>
            </div>
        </div>
    </div>
</div>
</template>


<script>
export default {
    name:"AddTodo",
    data(){
        return {
            title:''
        }
    },
        methods:{
        addTodo(e){
            e.preventDefault();
            const newTodo = {
                title: this.title,
                completed: false
            }
            this.$emit('add-todo', newTodo);
            this.title = '';
           }
        }
}
</script>