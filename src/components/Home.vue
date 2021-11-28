<template>
    <h1>Home Component</h1>
    <button v-on:click= "test()">CLick Me</button>
    <button v-on:click= "change()">Phone</button>
    <input type="text" v-model="increment"/>
    <br/><br/>
    <input type="text" placeholder="enter email" v-model="email"/>
    <br/><br/>
    <input type="password" placeholder="enter password" v-model="password"/>
    <br/><br/>
    <button v-on:click= "change()">Get Data</button>
    <h2>{{email}}</h2>
    <h3>{{mobile}}</h3>
    <h3>{{mobile==101010}}</h3>
    <h3>{{increment}}</h3>
    <h4>{{getname("maruf")}}</h4>
    <h4>{{getName("Nishan")}}</h4>
    <h4>{{getData()}}</h4>
    <h4>{{getData().name}}</h4>
    <h4>{{getData().email}}</h4>

    <h1>Get CheckBox & Radio Buttton Value</h1>
    <h3>Technology</h3>
    <label for="java">Java</label>
    <input type="checkbox" value="java" id="java" v-model="technology">
    <label for="php">Php</label>
    <input type="checkbox" value="php" id="php" v-model="technology">
    <label for="node">node</label>
    <input type="checkbox" value="node" id="node" v-model="technology">
    <br/><br/>
    <h3>Who I Am ?</h3>
    <label for="student">Student</label>
    <input type="radio" value="student" id="student" name="who" v-model="me"/>
    <label for="daveloper">Daveloper</label>
    <input type="radio" value="daveloper" id="daveloper" name="who"  v-model="me"/>
    <h4>Selected Technology : {{technology}}</h4>
    <h4>Selected Who Am I : {{me}}</h4>
    <br/><br/>
    <h2 v-if="show">If Condition</h2>
    <h2 v-else>Else Condition</h2>
    <button v-on:click="show=!show">Show</button>
    <h1>For Loop In VueJs</h1>
    <ul>
        <li v-for="x in friends" :key="x">{{x}}</li>
    </ul>
    <br/><br/>
    <ul>
        <li v-for="x in user" :key="x.name">
            Name Is :{{x.name}} And Email Is : {{x.email}}
            </li>
    </ul>
    <br/><br/>
    <Child name="Maruf Nishan" :details="child" :getalert="childtest"/>
    <br/><br/>
    <h1>Reuse Component</h1>
    
    <ul>
        <li v-for="x in users" :key="x.name">
            <User :data="x" :reuse="reusedata"/>
            </li>
    </ul>
    <h1>Html Binding</h1>
    <div v-html="tag"></div>
    <div v-html="tag2"></div>
    <br/><br/>
    <h1>CSS Binding</h1>
    <div :class="applyStyle">
        <h2 >Home Component Css Binding</h2>
    </div>
        <button v-on:click="colourfool=!colourfool">Apply Style</button>
    <Student name="Student Maruf" :getUser="myname"/>
    <br/><br/>
    <Teacher teacher="Abid Sir"/>
    <h2>{{fromChild}}</h2>
</template>





<script>
import Child from './Child.vue'
import User from './User.vue'
import Student from './Student.vue'
import Teacher from './Teacher.vue'
 export default {
     name:'Home',
     components: {
         Child,
         User,
         Student,
         Teacher
     },
     data(){
         return{
             email:null,
             mobile:'01718863771',
             password:null,
             increment:10,
             technology:[],
             me:null,
             show:false,
             friends:['Murad','Tusar','Mobin','Riad'],
             child:{name:'sabbir',email:'sabbir@test.com'},
             user:[
                 {
                     name:"Murad",
                     email:"murad@gmail.com"
                 },
                 {
                     name:"Tusar",
                     email:"tusar@gmail.com"
                 },
                 {
                     name:"Mobin",
                     email:"mobin@gmail.com"
                 },
                 {
                     name:"Riad",
                     email:"riad@gmail.com"
                 }
             ],
             getname:function(a){
                 return a;
             },
             users:[
                 {name:'Sabbir',email:'sabbir@test.com'},
                 {name:'Murad',email:'murad@test.com'}
             ],
             tag:"<h1>Maruf Html Binding</h1>",
             tag2:"<h1>Maruf Html Binding2</h1>",
             colourfool:false,
             fromChild:"",
         }        
     },
     methods:{
             getName(name){
                 return name
             },
             getData(){
                 return{
                     name:'Maruf Nishan',
                     email:this.email,
                     password:this.password,
                     mobile: this.mobile
                 }
             },
             change(){
                 this.mobile='01708582044',
                 this.increment=this.increment+1,
                 console.warn("values :",this.email,this.password)
             },
             test(){
                 alert("Function Called");
             },
             childtest(){
                 console.warn("Parent Function Called"),
                 alert("Hi From Home Componet");
             },
             reusedata(name){
                 alert(name)
             },
             myname(name){
                 alert(name),
                 this.fromChild=name
             },
             
         },
    computed:{
        applyStyle(){
            return {
            green:this.colourfool,
            err:true,
            other:true
        }
        }
    }
 }
</script>





<style scoped>
    h1{
        color: orange;
    }
    .green{
        background-color: greenyellow;
        width: 400px;
        padding: 10px;
        margin: auto;
    }
    .err{
        color: red;
    }
    .other{
        font-size: 20px;
    }
</style>