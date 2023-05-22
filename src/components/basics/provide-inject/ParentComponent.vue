<template>
  <div class="bg-info">
    <h2>Parent Component for DI</h2>
    <!-- Message: <input type="text" v-model/> <ChildComponent /> -->
    <ChildComponent />
  </div>
</template>

<script lang="ts">
import { defineComponent, provide, ref } from "vue";
import { ChildComponentKey } from "./ChildComponentKey";
import ChildComponent from "./ChildComponent.vue";

export default defineComponent({
  name: "ParentComponent",
  components: { ChildComponent },
  setup() {
    const message = ref("provide injection in Vue3");
    provide(ChildComponentKey, { message });
    return { message };
  },
});
</script>
