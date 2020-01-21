<template>
    <div>
       <p><h3>To do list: </h3><p/>
       Date <input type="text">  To do <input type="text"><br><br>

       <!--create button-->
       <!-- <button class="btn btn-success"  v-on:click ="SaveData"> Save Data </button>  -->
       <!-- <button class="btn btn-info" v-on:click ="LoadData()"> Render table </button><br><br> -->

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
                <!-- <th scope="row">{{1}}</th> -->
                <td>{{ls.task}}</td>
                <td>{{ls.time}}</td>
                <td>
                     <button class="btn btn-info"  > Done </button>
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
            list: [
                {   time : "Monday 09:30 am",
                    task : "Big cleaning"
                },
                {   time : "Tuesday 13.00 pm",
                    task : "Shopping"
                },
                 {  time : "Wednesday 14:00 pm",
                    task : "meeting"
                }
            ]
        }
    }, 

 } 

</script>

<style>
    @import url("https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css")
</style>