import firebase fr
<template>
    <div id="app" class="container">
        <div class="page-header">
            <h1>Vue.js & Firebase <small>Todo Application</small></h1>
        </div>
        <div class="card">
            <div class="card-body">
                <h3 class="card-title">Add New Todo</h3>
                <label for="bookTitle">Title:</label>

                <input type="text" v-model="newTask" class="form-control">
                <br>
                <button type="button" class="btn btn-info" v-on:click="addTodo()">
                    Add Todo
                </button> 
            </div>
        </div>
        <br>
        <div class="card">
            <div class="card-body">
                <h3 class="card-title">Todo List</h3>
                <table class="table table-striped">
            <thead>
                <tr>
                    <th>#</th>
                    <th>Todo</th>
                    <th></th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>1</td>
                    <td>bbb</td>
                    <td><span class="glyphicon glyphicon-trash" aria-hidden="true"></span></td>
                </tr>
                <!-- <tr v-for="book in books">
                    <td><a v-bind:href="book.url">{{book.title}}</a></td>
                    <td>{{book.author}}</td>
                    <td><span class="glyphicon glyphicon-trash" aria-hidden="true" v-on:click="removeBook(book)"></span></td>
                </tr> -->
            </tbody>
            </table>
        </div>
    </div>
  </div>
</template>

<!--firebase config-->
<script src="https://www.gstatic.com/firebasejs/7.7.0/firebase-app.js"></script>
<script src="https://www.gstatic.com/firebasejs/7.7.0/firebase-firestore.js"></script>

<script>
    import { firebase } from "@firebase/app";
    import "@firebase/firestore";
       
    var firebaseConfig = {
        apiKey: "AIzaSyBGXFuW2-dgcqzr2Qi3FJHHUNgqchi6qNw",
        authDomain: "mytodo-9c7de.firebaseapp.com",
        databaseURL: "https://mytodo-9c7de.firebaseio.com",
        projectId: "mytodo-9c7de",
        storageBucket: "mytodo-9c7de.appspot.com",
        messagingSenderId: "971316618674",
        appId: "1:971316618674:web:d3644e81ae09d909f630ab"
    };

    firebase.initializeApp(firebaseConfig);
    var db = firebase.firestore(); 

    export default{
        data(){
            return{
                todos:[],
                newTask:'' 
            }
        },
        firestore(){
            return{
                todos:db.collection('todos'),
            }
        },
        methods:{
            addTodo(){
                db.collection('todos').add({
                    task : this.newTask,
                    timestamp : new Date(),
                }); 
               }
            }
    }
</script>

<style>
    @import url("https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css");
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 20px;
}
</style>
