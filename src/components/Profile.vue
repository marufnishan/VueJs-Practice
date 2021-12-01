<template>
    <div>
        <h1>Name: {{profileName}}</h1>
        <p>Email: {{profileName}}@gmail.com</p>
    </div>
</template>
<script>
import {useRoute} from 'vue-router'
export default{
    name:'Profile',
    data(){
        return{
            profileName:''
        }
    },
    mounted()
    {
        const route=useRoute();
        console.warn("route",route.params.name);
        this.profileName=route.params.name
    }
}
</script>
<style scoped>

</style>