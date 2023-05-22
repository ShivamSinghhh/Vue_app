<template>
  <div>
    <h2 class="bg-warning text-center">Vue 3 with Typescript & Pinia</h2>
    <!-- <DirectiveDemo /> -->
    <!-- <JobApp /> -->
    <!-- <WatchDemo /> -->
    <!-- <ParentComponent /> -->
    <LifeCycleComponent />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
// import DirectiveDemo from "@/components/basics/DirectiveDemo.vue";
// import JobApp from "../JobApp.vue";
// import WatchDemo from "@/components/basics/WatchDemo.vue";
// import ParentComponent from "@/components/basics/provide-inject/ParentComponent.vue";
import LifeCycleComponent from "@/components/basics/lifecycle/LifeCycleComponent.vue";

//import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

export default defineComponent({
  name: "HomeView",
  components: {
    // DirectiveDemo,
    //JobApp,
    // WatchDemo,
    // ParentComponent,
    LifeCycleComponent,
  },
});
</script>
