<template>
  <div class="bg-warning">
    <h1 class="text-primary">{{ message }}</h1>
    <h3>Login Form</h3>
    Username <input type="text" ref="username" />
    <br />
    Password <input type="password" ref="password" value="welcome" />
    <br />
    <button class="btn btn-success">Login</button>
  </div>
</template>
<script setup lang="ts">
import { ref, onMounted, onUpdated, onBeforeUnmount } from "vue";
const message = ref<string>("Learning lyfle cycle");
const username = ref<HTMLInputElement | null>(null);
const password = ref<HTMLInputElement | null>(null);

onMounted(() => {
  // this is fired only once, initialize data with fetch(url) and update state
  //make ajax calls ,  to subscribe to web sockets  or observables, custom events
  username.value?.focus;
  console.log("onMouted is fired");
});
onUpdated(() => {
  //this is called every time when state changes
  console.log("onUpdate fired ....");
});
onBeforeUnmount(() => {
  // fired only once, clean the data/cache,unscribe web sockets/objervables (memory leaks)
  console.log("onBeforeUnmount is fired...");
});
</script>
