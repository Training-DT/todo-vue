<template>
    <div>
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
    @import url("https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css")
</style>