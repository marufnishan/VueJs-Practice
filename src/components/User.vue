<template>
    <div class="user">
        <h2>{{data.name}}</h2>
        <h2>{{data.email}}</h2>
        <button v-on:click="reuse(data.name)">Alert Name</button>
        <h3>Nishan</h3>
        <h3 v-bind="$attrs">Maruf</h3>
    </div>
</template>
<script>
    export default{
        name:'User',
        props:{
            data:Object,
            reuse:Function
        }
    }
</script>
<style scoped>
    .user{
        background-color: green;
        padding: 10px;
        border-bottom: 1px solid;
        margin-bottom: 20px;
    }
</style>
