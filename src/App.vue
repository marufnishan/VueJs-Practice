<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to My First Vue.js App"/>
  <router-link to="/">Home</router-link><br><br>
  <router-link to="/login">Login</router-link><br><br>
  <router-link to="/profile/Maruf">Maruf Profile</router-link><br><br>
  <router-link to="/profile/Murad">Murad Profile</router-link><br><br>
  <router-link to="/profile/Tusar">Tusar Profile</router-link><br><br>
  <h1>Call Api</h1>
  <p v-for="item in list" :key="item">
    Id: {{item.id}}<br>
    Email: {{item.email}}<br>
    First Name: {{item.first_name}}<br>
    Last Name: {{item.last_name}}<br><br>
    <img :src="item.avatar" alt=""><br><br>
  </p>
  <router-view></router-view>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import axios from 'axios'
export default {
  name: 'App',
  data()
  {
    return{
      list:[]
    }
  },
  async mounted()
  {
    let result = await axios.get("https://reqres.in/api/users?page=1");
    console.warn("api data",result.data.data);
    this.list=result.data.data;
  },
  components: {
    HelloWorld,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
