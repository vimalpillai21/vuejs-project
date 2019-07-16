<template>
    <div class="container" align="center">
        Register
        <table class="table table-responsive" v-if="showtable">
            <tr>
                <th>Key</th>
                <th>id</th>
                <th>Employee Name</th>
                <th>Employe Salary</th>
                <th>Employee Age</th>
                <!-- <th>Profile Image</th> -->
            </tr>
            <tr v-for="res, key in results" v-on:click="deleteElement(key)">
                <td>{{ key }}</td>
                <td>{{ res.id }}</td>
                <td>{{ res.employee_name }}</td>
                <td>{{ res.employee_salary }}</td>
                <td>{{ res.employee_age }}</td>
                <!-- <td>{{ res.profile_image }}</td> -->
            </tr>
        </table>
    </div>
</template>

<script>
import Vue from 'vue/dist/vue.js';
import axios from 'axios';
export default {
    data(){
        return{
            showtable: false,
      results: []  
        }
    },
    mounted(){
        axios.get('http://dummy.restapiexample.com/api/v1/employees').then(
            res => {
                // console.log(res.data);
                this.results = res.data;
                console.log('results - ',this.results);
                this.$root.$emit('register axios message','Hello','World');
                console.log('Event Emitted');
                this.showtable = true;
            },
            err => {
                console.log(err);
            }
        )
    },
    methods:{
        deleteElement(key){
            // console.log(key);
            let arrayElement = this.results[key];
            let indexNumber = this.results.indexOf(arrayElement);
            let splicedArray = this.results.splice(indexNumber,1);
            console.log(splicedArray);

        }
    }

}
</script>

