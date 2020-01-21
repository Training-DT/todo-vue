import firebase fr
<template>
    <div>
        <h1 style = "color: blueviolet">Add to do list </h1>
        Task : <input type="text" v-model="newTask">
        <button type="button" 
                class="btn btn-info" 
                v-on:click="addTodo()">
            Add Todo
        </button><br/><br/>     
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
    @import url("https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css")
</style>
