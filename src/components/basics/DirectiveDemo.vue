<template >
    <div class="bg-info">
    <h2 v-text="message"></h2>
    username:
    <input type="text" v-model="inputValue"/>
    <button class="btn btn-primary ml-10" v-on:click="handleClick">Click me</button>
    <ul>
        <li v-for="(item,index) in items" :key="index" v-text="item" ></li>
    </ul>
   
    <div v-if="showDiv">Yes. You are a member </div>
    <div v-html="htmlContent"></div>
    <a :href="url" v-bind:title="linkTitle">Yahoo</a>
    <img :src="imageUrl" v-bind:alt="imageAlt"/>
 
    </div>
</template>

<script setup lang="ts">
 import {ref} from "vue"

 const imageUrl=ref('path/to/image.jpg')
 const imageAlt=ref('capgemini image')

const linkTitle=ref("Visit yahoo.com")
 const message=ref("Hello , Vue3")
 const inputValue=ref(' ')
 const showDiv=ref(true)
 const items=ref(['Computer','Keboard','Mouse'])
 const htmlContent=ref(' <span>Learning directives</span>')
 const url=ref('http://www.yahoo.com')

const handleClick= (event:Event)=>{
    alert("Thanks... Button is clicked")
}
</script>

<style scoped>
div {
    margin:10;
    border:1px red;
    border-radius:30px;
}
</style>