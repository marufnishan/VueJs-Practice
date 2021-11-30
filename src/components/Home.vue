<template>
<h1>Home Component</h1>
<button v-on:click="test()">CLick Me</button>
<button v-on:click="change()">Phone</button>
<input type="text" v-model="increment" />
<br /><br />
<input type="text" placeholder="enter email" v-model="email" />
<br /><br />
<input type="password" placeholder="enter password" v-model="password" />
<br /><br />
<button v-on:click="change()">Get Data</button>
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
<br /><br />
<h3>Who I Am ?</h3>
<label for="student">Student</label>
<input type="radio" value="student" id="student" name="who" v-model="me" />
<label for="daveloper">Daveloper</label>
<input type="radio" value="daveloper" id="daveloper" name="who" v-model="me" />
<h4>Selected Technology : {{technology}}</h4>
<h4>Selected Who Am I : {{me}}</h4>
<br /><br />
<h2 v-if="show">If Condition</h2>
<h2 v-else>Else Condition</h2>
<button v-on:click="show=!show">Show</button>
<h1>For Loop In VueJs</h1>
<ul>
    <li v-for="x in friends" :key="x">{{x}}</li>
</ul>
<br /><br />
<ul>
    <li v-for="x in user" :key="x.name">
        Name Is :{{x.name}} And Email Is : {{x.email}}
    </li>
</ul>
<br /><br />
<Child name="Maruf Nishan" :details="child" :getalert="childtest" />
<br /><br />
<h1>Reuse Component</h1>

<ul>
    <li v-for="x in users" :key="x.name">
        <User :data="x" :reuse="reusedata" />
    </li>
</ul>
<h1>Html Binding</h1>
<div v-html="tag"></div>
<div v-html="tag2"></div>
<br /><br />
<h1>CSS Binding</h1>
<div :class="applyStyle">
    <h2>Home Component Css Binding</h2>
</div>
<button v-on:click="colourfool=!colourfool">Apply Style</button>
<Student name="Student Maruf" :getUser="myname" />
<br /><br />
<Teacher teacher="Abid Sir" />
<h2>{{fromChild}}</h2>
<h1>Ref in Vue JS 3</h1>
<input type="text" ref="input" />
<button v-on:click="getRef">Click Me</button>
<br /><br />
<h1>Simple Form</h1>
    <ul>
        <li style="color:red" v-for="item in error" v-bind:key="item">
            Opps ... {{item}} is not valid  ! ! !
        </li>
    </ul>
<form>
    <label>Name :</label>
    <input type="text" placeholder="enter name.." v-model.trim="form.name"/>
    <br /><br />
    <label>Email :</label>
    <input type="text" placeholder="enter email.." v-model.trim.lazy="form.email"/>
    <br /><br />
    <label>Phone :</label>
    <input type="Number" placeholder="enter number.." v-model.number="form.number"/>
    <br /><br />
    <label>Password :</label>
    <input type="password" placeholder="enter password.." v-model="form.password"/>
    <br /><br />
    <label>Country :</label>
    <select v-model="form.country">
        <option >Bangladesh</option>
        <option >USA</option>
        <option >Germany</option>
    </select>
    <br /><br />
    <h3>Technology</h3>
    <label for="php">PHP :</label>
    <input type="checkbox" value="php" v-model="form.technology"/>
    <br /><br />
    <label for="java">Java :</label>
    <input type="checkbox" value="java" v-model="form.technology"/>
    <br /><br />
    <h3>Gender</h3>
    <label>Male :</label>
    <input type="radio" value="male" name="gender" v-model="form.gender"/>
    <br /><br />
    <label>Female :</label>
    <input type="radio" value="female" name="gender"  v-model="form.gender"/>
    <br /><br />
    <button type="button" v-on:click="login">Login</button>
    <br /><br />
    <p>
        {{form}}
    </p>
</form>
    <br /><br />
    <h1>Non-Props Data</h1>
    <NonPrPS datas="some data"/>
    <br /><br />
    <h1>Computed Property</h1>
    <h2>{{getReasult}}</h2>
    <h2>{{getReasult}}</h2>
    <h2>{{getReasult}}</h2>
    <h2>{{getReasult}}</h2>
    <h2>{{getReasultMethods()}}</h2>
    <br /><br />
    <h1>Watchers With Example</h1>
    <h1>{{count}}</h1>
    <button v-on:click="count=count+1"> + </button><br/><br/>
    <button v-on:click="count=count-1"> - </button>
    <br /><br />
    <h1>Slots With Example</h1>
    <h2>Childs Component</h2>
    <Childs>
        <template v-slot:h1 >
            <h2 >Sabbir</h2>
        </template>
        <template v-slot:content >
            <h2>Content From Home Component Slot</h2>
        </template>
        <template v-slot:btn >
        <button>Buy Now</button>
        </template>
    <br /><br />
    </Childs>
    <Childs>
        <template v-slot:h1 >
            <h2 >Maruf</h2>
        </template>
        <template v-slot:content >
            <h2>Content From Home Component Slot</h2>
        </template>
        <template v-slot:link >
            <a href="#" >Hi From Home Component Slot link</a>
        </template>
        <template v-slot:image >
            <img src="../assets/imge.jpeg">
        </template>
    <br /><br />
    </Childs>
    <br /><br />
    <h1>Dynamic Component</h1>
    <button v-on:click="tab='Php'">Load Php</button>
    <button v-on:click="tab='Java'">Load Java</button>
    <button v-on:click="tab='Node'">Load Node</button>
    <component :is="tab"/>
    <teleport to="#footer">
    <Footer/>
    </teleport>
</template>

<script>
import Child from './Child.vue'
import User from './User.vue'
import Student from './Student.vue'
import Teacher from './Teacher.vue'
import NonPrPS from './NonPrPS.vue'
import Childs from './Childs.vue'
import Php from './Php.vue'
import Java from './Java.vue'
import Node from './Node.vue'
import Footer from './Footer.vue'
export default {
    name: 'Home',
    components: {
        Child,
        User,
        Student,
        Teacher,
        NonPrPS,
        Childs,
        Php,
        Java,
        Node,
        Footer
    },


    data() {
        return {
            email: null,
            mobile: '01718863771',
            password: null,
            increment: 0,
            count:0,
            technology: [],
            me: null,
            show: false,
            friends: ['Murad', 'Tusar', 'Mobin', 'Riad'],
            child: {
                name: 'sabbir',
                email: 'sabbir@test.com'
            },
            user: [{
                    name: "Murad",
                    email: "murad@gmail.com"
                },
                {
                    name: "Tusar",
                    email: "tusar@gmail.com"
                },
                {
                    name: "Mobin",
                    email: "mobin@gmail.com"
                },
                {
                    name: "Riad",
                    email: "riad@gmail.com"
                }
            ],
            getname: function (a) {
                return a;
            },
            users: [{
                    name: 'Sabbir',
                    email: 'sabbir@test.com'
                },
                {
                    name: 'Murad',
                    email: 'murad@test.com'
                }
            ],
            tag: "<h1>Maruf Html Binding</h1>",
            tag2: "<h1>Maruf Html Binding2</h1>",
            colourfool: false,
            fromChild: "",
            form:{
                name:'',
                email:'',
                number:'',
                password:'',
                country:'',
                technology:[],
                gender:''
            },
            error:[],
            dollors:100,
            tk:84,
            discount:10,
            tab:'Java'
            
        }
    },



    methods: {
        getName(name) {
            return name
        },
        getData() {
            return {
                name: 'Maruf Nishan',
                email: this.email,
                password: this.password,
                mobile: this.mobile
            }
        },
        change() {
            this.mobile = '01708582044',
                this.increment = this.increment + 1,
                console.warn("values :", this.email, this.password)
        },
        test() {
            alert("Function Called");
        },
        childtest() {
            console.warn("Parent Function Called"),
                alert("Hi From Home Componet");
        },
        reusedata(name) {
            alert(name)
        },
        myname(name) {
            alert(name),
                this.fromChild = name
        },
        getRef() {
            this.$refs.input.focus();
            let val = this.$refs.input.value;
            console.warn(val);
            this.$refs.input.style.color = "red"
        },
        login(){
            this.error=[];
            for(const item in this.form)
            {
                if(this.form[item]==="" || this.form[item].length===0 )
                {
                    this.error.push(item)
                }
            }
            console.warn("login data",this.form,this.error);

            if(this.error.length===0){
                alert("Data Has Been Submitted!")
            }
        },
        getReasultMethods()
        {
            return (this.dollors*this.tk)-this.discount;
        },

    },



    computed: {
        applyStyle() {
            return {
                green: this.colourfool,
                err: true,
                other: true
            }
        },
        getReasult(){
            return (this.dollors*this.tk)-this.discount;
        },
    },

    watch:{
                count(val,prev)
                {
                    
                    if(val>5){
                        alert("Grater Then 5 Val")
                    }
                    if(val>7){
                        alert(prev);
                        this.count=0;
                    }
                }
            }
}
</script>

<style scoped>
h1 {
    color: orange;
}

.green {
    background-color: greenyellow;
    width: 400px;
    padding: 10px;
    margin: auto;
}

.err {
    color: red;
}

.other {
    font-size: 20px;
}
</style>
