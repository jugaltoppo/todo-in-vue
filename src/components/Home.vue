<template>
    <div id="todo">
        <form @submit.prevent="addTodo" >
            <input v-model="todo">
            <button>Add todo</button>
        </form>
        <table border="1">
            <thead>
                <tr>
                    <th>task</th>
                    <th>Action</th>
                </tr>
            </thead>
                    <tbody>
                       <tr v-for="todo in todos" :key="todo.id"><td>{{todo.text}}</td> <td><button :value="todo.text" @click="removeTodo(todo)">X</button></td></tr>
                   </tbody>
        </table>
    </div>
</template>

<script>
export default {
   data(){
       return {
           todos: [],
           todo: ""
       }
   },
   methods : {
       addTodo: function(){
           if(this.todo.length>1){
                this.todos.push({id: this.todos.length, text: this.todo});
                this.todo="";
           }
       },
       removeTodo: function(value){
           let index=this.todos.filter((tdo)=>{
               return tdo.id!==value.id
           })
           this.todos=index;
       }
   }
}
</script>

<style>
    #todo{
        width: 30%;
        margin-left: auto;
        margin-right: auto;
        text-align: left;
    }
    form, table{
        text-align: center;
    }
    table{
        margin: 1rem auto;
    }
</style>