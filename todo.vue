<template>
    <div>
       <p><h3>To do list: </h3><p/>
       Date <input type="text">  To do <input type="text"><br><br>

       <!--create button-->
       <!-- <button class="btn btn-success"  v-on:click ="SaveData"> Save Data </button>  -->
        <button class="btn btn-info"  v-on:click ="LoadData"> Render table </button><br><br>

        <table class="table">
            <thead class="thead-dark">
                <tr>
                <th scope="col">date</th>
                <th scope="col">todo</th>
                <th scope="col">note</th>
                 <th scope="col">button</th> 
                </tr>
            </thead>
            <tbody>
                <tr v-for="(user, index) in users" v-bind:key="user.id"> 
                <th scope="row">{{index+1}}</th>

                <td>{{user.date}}</td>
                <td>{{user.do}}</td>
                <td>{{user.note}}</td>
                <td>
                     <button class="btn btn-danger"  v-on:click ="remove(index)"> Delete </button>
                </td>
                </tr>
            </tbody>
        </table>      
    </div>
</template>

<script>
export default { 
    data() {  //attribute
        return {
            users: []
        }
    }, 
    methods: {
        
        LoadData(){
            fetch('https://jsonplaceholder.typicode.com/users')
            .then(response => response.json())
            .then(json => {
                this.users = json
            })
        },
        remove(index){
            this.users.splice(index ,1)
        }
    },
    
}
</script>

<style>
    @import url("https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css")
</style>