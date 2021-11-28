<template>
    <h1>Teacher Component</h1>
    <h2>Teacher Name From Home Component Using Props : {{teacher}}</h2>
</template>


<script>
    export default{
        name:'Teacher',
        props:{
            teacher:String
        }
    }
</script>


<style scoped>
    h1{
        color: orange;
    }
</style>
