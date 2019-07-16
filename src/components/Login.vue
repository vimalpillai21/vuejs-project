<template>
    <div id="login">
       <h1>Login</h1>
       <hr>
       <form class="form col-6 mx-auto">
           <div class="form-group row">
           <label class="col-4" for="username">Username</label>
           <input type="text" maxlength="30" class="form-control col-4" id="username" v-model="name" />
           </div>
           <div class="form-group row">
           <label class="col-4" for="password">Salary</label>
           <input type="text" maxlength="30" class="form-control col-4" id="password" v-model="salary" />
           </div>
           <div class="form-group row">
           <label class="col-4" for="age">Age</label>
           <input type="text" maxlength="30" class="form-control col-4" id="age" v-model="age" />
           </div>
           <button class="btn btn-primary" v-on:click="submit()">Login</button>
       </form>
       <Child />
    </div>
</template>

<script>
import Vue from 'vue/dist/vue.js';
import Child from './Child';
import axios from 'axios';
export default {
    data(){ 
        return {
            name:'hello',
            salary:'32434',
            age:'23'
        }
    },
    mounted(){
        // this.$root.$on('register axios message',(arg1,arg2) =>{
        //     console.log('arg1 - ',arg1);
        //     console.log('arg2 - ',arg2);
        // });
    },
    methods :{
        submit(){
            console.log("Hello world submitted");
            console.log('Username - ',this.userName);
            console.log('Password - ',this.passWord);
            // axios.post('http://dummy.restapiexample.com/api/v1/create',
            // {
            //     name : this.name,
            //     salary : this.salary,
            //     age : this.age
            // }
            // ).then(
            //     res => {
            //         console.log(res.data);
            //     },
            //     err => {
            //         console.log(err);
            //     }
            // )
            this.$root.$on('register axios message', (arg1,arg2)=>{
                console.log('arg1 -',arg1);
                console.log('arg2 -',arg2);
            });
        }
    },
    components:{
        Child,
    } 
}
</script>
<style>
label{
    color: red;
}
</style>


