<template>
    <h1>Student Component</h1>
    <h2>Student Name From Home Component Using Props:{{name}}</h2>
    <button v-on:click="getUser(studentName)">Send Name</button>

</template>


<script>
    export default{
        name:'Student',
        data(){
            return{
                studentName:"Maruf Nishan I Am From Child"
            }
            
        },
        props:{
            name:String,
            getUser:Function
        }
        
    }
</script>


<style scoped>
    h1{
        color: orange;
    }
</style>
