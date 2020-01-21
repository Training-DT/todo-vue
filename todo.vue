<template>
    <div id="app" class="container">
        <div class="page-header">
            <h1>Vue.js & Firebase <small>Todo Application</small></h1>
        </div>
        <div class="card">
            <div class="card-body">
                <h3 class="card-title">Add New Todo</h3>
                <label for="bookTitle">Title:</label>
                <input type="text" id="bookTitle" class="form-control">
                <br>
                <input type="submit" class="btn btn-primary" value="Add Todo">
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