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
                <table class="table">
                    <thead class="thead-dark">
                        <tr>
                            <th scope="col">task</th>
                            <th scope="col">Time</th>
                            <th scope="col">Done</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="(ls) in list" v-bind:key="ls.id"> 
                            <td>{{ls.task}}</td>
                            <td>{{ls.time}}</td>
                            <td>
                                <button class="btn btn-info"  > Done </button>
                            </td>
                        </tr>
                    </tbody>
                </table> 
        </div>
    </div>
  </div>
</template>

<script>
export default { 
    data() { 
        return {
            list: [
                {   
                    time : "Monday 09:30 am",
                    task : "Big cleaning"
                },
                {   
                    time : "Tuesday 13.00 pm",
                    task : "Shopping"
                },
                 {  
                     time : "Wednesday 14:00 pm",
                    task : "meeting"
                }
            ]
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