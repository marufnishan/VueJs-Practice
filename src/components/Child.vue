<template>
<h1>Child Component</h1>
<h2>{{name}}</h2>
<h2>{{details.name}}</h2>
<h2>{{details.email}}</h2>
<button v-on:click="getalert()">Call Function</button>
</template>

<script>
    export default {
        name: 'Child',
        props:{
            name:String,
            details:Object,
            getalert:Function
        }
    }
</script>
<style scoped>
    h1{
        color: orange;
    }
</style>
