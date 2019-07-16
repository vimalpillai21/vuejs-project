<template>
    <div>
        Hello message
        <button class="btn btn-default btn-sm" v-on:click="toggleButton()">Hello</button>
        <p v-if="show">Hello from child component!</p>
    </div>
</template>
<script>
export default {
    name: 'Child',
    data(){
        return{
            show:false
        }
    },
    methods:{
        toggleButton(){
            if(this.show){
                this.show = false;
            }else{
                this.show = true;
                this.$router.push('register');
            }
        }
    }
}
</script>

