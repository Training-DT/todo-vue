<template>
    <div>
        <h1 style = "color: blueviolet">Add to do list </h1>
        Task : <input type="text"><br/><br/>
        Due Date : <input type="text"><br/><br/>    
        <button type="button" 
                class="btn btn-info" 
                v-on:click="saveTodo()">
        Save</button><br/><br/> 
        <p>{{this.taskTodo}}</p>
        <p>{{this.dueDate}}</p>
    </div>
</template>

<script>

    export default{
        data(){
            return{
                taskTodo:"",
                dueDate:"",
            }
        },
        methods:{
            saveTodo(){
               this.taskTodo = document.body.children[0].children[1].value;
               this.dueDate = document.body.children[0].children[4].value;
              
              // console.log("save !");
              // console.log(this.dueDate);
               }
            }
    }


</script>

<style>
    @import url("https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css")
</style>
