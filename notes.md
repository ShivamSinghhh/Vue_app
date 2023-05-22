Node version should be > 16 for Vue-3
node -v 
v18.16.0

vue create hello-world
cd project-name
npm run serve

vue create dummy-app
vue-3
manual select features
3x
class - N
babel -y
eslint- enter
enter
enter
no

extension
volar - vue language features & typescript

//----------------------------------------------------------------//
ECMA: specifications - ES5 : object based lang - function. object.
ES 6 : React - jsx => object oriented tech. - 16 new features
-let, const, FAO,OD,class , extends,static, Temp,lit,spread , rest , Promise , fetch....

Babel compiler - ES6 to ES5
Typescript: Pure OOL
Typesafe, stronlgly typed with generics <T>
var data:customer[]=[{},{}]
interface , abstract class, enum,
public , private , protected
......
npm install typescript
tsc app.ts => app.js
TS <=ES6/ES5
==================================
SOLID principles:
S: Single responsibility - Vue components-one comp- one task(resp)- component tree => DOM tree

    Open/closed principle:  make change by overriding existing api w/o tampering API.
    class demo extends DefineComponent{
        setup(){
            ...........
        }
    }

    LSP: depend on abstracts (interface ref) and not orignal    (Symbol)
    interface IBank{
        deposit(acno:number):void
    }
    const bank:IBank=new Bank()
    bank.deposit(101)

    Inteface segregation principle: break interfaces in  peaces
    //models customer, fligtManager
    interface IBank{
        deposit(....)
        withdraw(...)
        open()
        close()

    }
    interface IReport{
        report()
        mail()
    }
    interace Invoice()
    getInovice()
    }
    class Bank implements IBank{

    }
    class Order implements IReport, Invoice

## D: Dependency injection : provide/inject parent to child component

To define vue component : 2 ways

<script setup lang="ts">
    const name = ref("murthy") as string
</script>

defineComponent()

<template>{{msg}}</template>
msg="hello"

vue-directives

1.  Built in
    v-text ="msg" @text="msg"
2.  custom directives

v-for, (Grid), v-if="auth",v-show
v-model,v-html,....15 directives
v-grid

handle events:
v-on:click => @click="handler(event)"
v-once

Declarative function:

demo()
function demo(){
const company="CAPGEMINI"  
}

var fn=function(){ //callback
console.log('hi')
}
fn()

setTimeout(()=>{
console.log('hi')
},5000)

const fn=()=>{
console.log("hi")
}
=====================================================
options api vs composition API

name: name of component
props:defineProps(name)
components:[Child]
data(){
return {
name:'murthy' as string,
salary:2500
}
},
methods:{
handleClick(name)...
login(){}
},
let da=computed(){
return this.salary\*10/100
},
watch(salary){ }
provide/inject
watchEffect.....

var x=10 -Primitive type= call by value-copy -immutable
var y=x
y=20
console.log(x)//10

var obj1={x:10} object/array/function are call by ref. -call by ref. = mutable = state , prop=immutable
var obj2=obj1
obj2.x=20
console.log(obj1.x)//20

const store={...........}
mutable=>immutable

let obj2=Object.assign({},obj1) >immutable
obj2.x=20
obj1.x 10

let obj2={...obj1} //spread

{id:1} :JSON
const data=ref('hello')

---

mini project:
how to pass data to child :props
compute
watch/watchEffect
provide/inject
v-slots
login form

Container vs presentation:
container is intelligent/smart/heavy duty/resp comp.
state manager - parent

Prensentation: child / dump/lightweight

data=ref(10)//state
{{square}}
const square=computed((data,)=>{
return data\*data
}))
==============================
props with type safety (interface , type declaration)
passed multiple states
used default setup (u will convert to <script setup  lang='ts'>)
computed
PropType
styles
================================================
watch and watchEffect()

Sync call and async call to a function: Promise
fetch(url).then(resp=>customers.data=resp)
.error(err=>console.log(err))

npm install axios : CRUD = GET,POST, PUT , DELETE
axios.get(url).then(resp=>console.log(resp))

function LRT(){
return new Promise(resolve,reject)
// fetch(url) //complex logic
if (ok)
resolve(response)
else
reject(error)
}

function SRT(){
console.log('hi')
}
LRT()
.then( (result)=>console.log(result))
.error( (error)=>console.log(error))
SRT()

ES7:
awaitable pattern:
async/await

async function complexlogic(data){
try{
let result=await invoke(data)//return promise  
 let final=await store(result)
console.log("all done")
}catch(error)
}

complextlogic()
dosomeotherLogic()

<script setup>
import { ref, watch } from 'vue'

const question = ref('')
const answer = ref('Questions usually contain a question mark. ;-)')

// watch works directly on a ref
watch(question, async (newQuestion, oldQuestion) => {
  if (newQuestion.indexOf('?') > -1) {
    answer.value = 'Thinking...'
    try {
      const res = await fetch('https://yesno.wtf/api')
      answer.value = (await res.json()).answer
    } catch (error) {
      answer.value = 'Error! Could not reach the API. ' + error
    }
  }
})
</script>

<template>
  <p>
    Ask a yes/no question:
    <input v-model="question" />
  </p>
  <p>{{ answer }}</p>
</template>
=============================================
Life cycle = UI   - angular/react/vue
component - 3 phases
 1. birth   : mounted
 2. growth :state changes  beforeUpdate....
 3. death : unmouted

They are calling implicitly life cycle methods(hooks)
