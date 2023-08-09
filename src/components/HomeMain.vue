<template>
<h1>Interpollation </h1>
<h3>{{ "home".length }}</h3>
<h3>{{ name + "------> " + email }}</h3>
<h3>we can assign values in interpollation <br> updated mobile no: {{ mobile =10101 }} where as in data written as 9090
</h3>
<br><br>
<h1>Methods</h1>

<h3>Button---</h3>
<button v-on:click="getData()">Click</button>
<h3>{{ getname("Kabs") }}</h3>
<h3>Object : {{ getDetails() }}</h3>
<h3>Object's Name : {{ getDetails().name }}</h3>
<h3>data's email : {{ getDetails().email }}</h3>
<br><br><br>
<h1>Events</h1>
<p>Single Click</p>
<button v-on:click="btn1()">Click</button>
<br><br>
<p>Double Click</p>
<button v-on:dblclick="btn2()">Click</button>

<p>Click Count</p>
<button v-on:click="getCount()">Click</button>
<h2>Count : {{ count }}</h2>

<br><br><br>
<h1>Two way Bindings</h1>
<p>Binding both vue (template) and Model (Script). Initial value is based on we declare in the script</p>
<br>
<input type="text" v-model="datum">
<br>
<h2>{{ datum }}</h2>

<br><br><br>
<h1>Get input field values</h1>
<p>Getting input Values in Console after clicking the button</p>
<input type="text" placeholder="Email" v-model="username"><br><br>
<input type="text" placeholder="Password" v-model="password"><br><br>
<button type="button" v-on:click="getform()">Getdata</button>
<br><br>
<h3>Username: {{ username }} <br> Password : {{ password }}</h3>
<br><br><br>
<h1>Get checkbox and Radio button values</h1>
<br>
<h3>CheckBox</h3>
<label for="1">Kabs</label>
<input type="checkbox" value="Kabs" v-model="V6" id="1">

<label for="2">Sap</label>
<input type="checkbox" value="Sap" v-model="V6" id="2">

<label for="3">Chan</label>
<input type="checkbox" value="Chan" v-model="V6" id="3">

<label for="4">Barani</label>
<input type="checkbox" value="Barani" v-model="V6" id="4">

<label for="5">Kanna</label>
<input type="checkbox" value="Kanna" v-model="V6" id="5">

<label for="6">Ice</label>
<input type="checkbox" value="Ice" v-model="V6" id="6">

<h4>Team : {{ V6 }}</h4>

<h3>Radio</h3>
<label for="11">Topper</label>
<input type="radio" value="Topper" v-model="radio" id="11">

<label for="12">Average</label>
<input type="radio" value="Average" v-model="radio" id="12">

<label for="13">Improver</label>
<input type="radio" value="Improver" v-model="radio" id="13">

<h4>Category : {{ radio }}</h4>

<br><br><br>
<h1>If Else Condition</h1>
<br>
<h3 v-if="show">If Condition</h3>
<h3 v-else>Else Condition</h3>
<br>
<button v-on:click="show = true">Click</button>

<br><br><br>
<h1>For Loop</h1>
<br>

<ul>
    <li v-for="item in delta" :key="item">
        {{ item }}
    </li>

</ul>

<ul>
    <li v-for="item in users" :key="item.name">
        {{ item.name }} ---> {{ item.email }}
    </li>

</ul>
<ChildofHome hello="Child" :name="name" :data="users" />

<br><br>
<h1>Forms</h1>
<br>
<form>
    <label>Email :</label>
    <input type="email" placeholder="Enter the Email" v-model="form.email"><br><br>

    <label>Password :</label>
    <input type="password" placeholder="Enter the Password" v-model="form.password"><br><br>

    <label>Country :</label>
    <select v-model="form.country">
        <option value="India">India</option>
        <option value="Us">US</option>
        <option value="Russia">Russia</option>
        <option value="Uk">UK</option>
        <option value="Pakistan">Pakistan</option>
    </select><br><br>

    <label>Gender : </label>
    <label>Male</label>
    <input type="radio" value="Male" v-model="form.gender">

    <label> Female</label>
    <input type="radio" value="Female" v-model="form.gender"><br><br>

    <label>Skills : </label>
    <label>C</label>
    <input type="checkbox" value="C" v-model="form.skills">

    <label> Cpp</label>
    <input type="checkbox" value="Cpp" v-model="form.skills">

    <label> Python</label>
    <input type="checkbox" value="Python" v-model="form.skills">

    <label> Java</label>
    <input type="checkbox" value="Java" v-model="form.skills">

    <br><br>
    <button type="button" v-on:click="login()">Login</button>
    <br>

    <ul>

        <li v-for="item in error" v-bind:key="item">
            <!--for binding the data we're using v-bind -->
            {{ item }} Should be Filled
        </li>
    </ul>

</form>

<br><br>
<h1>Computed Properties</h1>
<p>It is same as Methods ...However, the difference is that computed properties are cached based on their reactive
    dependencies. </p>
<br>
<h3>Calculation by Methods- {{ getResult1() }}</h3>
<h3>Calculation by Computed Property- {{ computed }}</h3>
<br>
<br>
<h1>Reuse Components</h1>
<ul>
    <li v-for="item in users" v-bind:key="item">
        <UserHome :data="item"/>
    </li>
</ul>

<br>
<h1>Passing Data from Child to Parent</h1>
<br>
<h3>Child Name : {{ Childname }}</h3>
<ChildtoParent :result="getChildName"/>

<br>
<h1>Vue HTML Binding</h1>
<br>
<p>{{ htmlbinding }}</p>
<p v-html="htmlbinding"></p>
<p v-html="htmlbinding + htmlbinding1"></p>

<br>
<h1>Class Binding</h1>
<br>
<h3 class="green">Green Color</h3>
<h3 :class="{green: colorful}">Green Color</h3>
<button v-on:click="changecolor()">Change Color</button>

<br><br>

<h1>Ref in Vue Js</h1>
<br>
<input type="text" ref="input"> 
<button v-on:click="reffunc()">Click</button>


<br><br>

<h1>Slots in Vue Js</h1>
<br>

<p>Slots in Vue are used to send HTML content from the parent into the child component.</p>
<br>
<ChildforSlots><h2>HTML content printed from Parent to Child</h2> </ChildforSlots>
<ChildforSlots><h2> 2nd Line</h2> </ChildforSlots>
</template>

<script>
import ChildofHome from './ChildofHome.vue';
import UserHome from './UserHome.vue';
import ChildtoParent from './ChildtoParent.vue';
import ChildforSlots from './ChildforSlots.vue';
 
export default {
    name: "HomeMain",
    components: {
        ChildofHome,
        UserHome,
        ChildtoParent,
        ChildforSlots
    },
    data() {
        return {
            name: "Kabilan",
            email: "kabs@gmail.com",
            mobile: 9090,
            count: 0,
            datum: 0,
            username: null,
            password: null,
            V6: [],
            radio: null,
            show: false,
            dollar: 100,
            rupee: 70,
            discount: 10,
            Childname : '',
            htmlbinding : '<h3>Hukum Tiger ka Hukum </h3>',
            htmlbinding1 : '<h3>--- Adavadi Anand</h3>',
            colorful : false,
            delta: [
                "sapna",
                "kabilan",
                "aishu",
                "barani",
                "kanna",
                "chan"
            ],
            form: {
                email: '',
                password: '',
                country: '',
                gender: '',
                skills: []

            },
            error: [],
            users: [{
                    name: "sap",
                    email: "sap@123"
                },
                {
                    name: "kab",
                    email: "kab@123"
                },
                {
                    name: "chan",
                    email: "chan@123"
                }, {
                    name: "bar",
                    email: "bar@123"
                },
                {
                    name: "kan",
                    email: "kan@123"
                },
                {
                    name: "ice",
                    email: "ice@123"
                }
            ]

        }
    },
    computed: {
        computed() {
            return (this.dollar * this.rupee) - this.discount
        }
    },
    methods: {

        getData() {
            alert("Back poda Boomer");
        },
        getname(x) {
            return x;
        },
        getDetails() {
            return {
                name: "Kams",
                email: this.email,
                mobile: 1234
            }
        },
        btn1() {
            alert("Btn 1 Click");
        },
        btn2() {
            alert(" Btn Double Click");
        },
        getCount() {
            this.count += 1
        },
        getResult1() {
            return (this.dollar * this.rupee) - this.discount
        },

        getform() {

            console.log("Values : ", this.username, this.password);
        },
        login() {
            this.error = []
            for (const item in this.form) {
                if (this.form[item] === "" || this.form[item].length === 0) {
                    this.error.push(item);
                }
            }
            if (this.error.length === 0) {
                alert("Data has been Submitted Successfully");
            }

            console.warn(this.form)
        },
        getChildName(Childname){
            this.Childname = Childname

        },
        changecolor(){
            this.colorful =!this.colorful
        },
        reffunc(){
            this.$refs.input.focus();
            this.$refs.input.value = "Poda Boom Boom Boomer";
            this.$refs.input.style.color = "Red";
        }

    }
}
</script>

<style scoped>
h1 {
    color: blue;
}
.green{
    color: green;
}
</style>
