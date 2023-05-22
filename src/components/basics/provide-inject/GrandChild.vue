<!-- eslint-disable no-undef -->
<!-- eslint-disable vue/valid-template-root -->
<template>
  <div class="bg-danger text-warning">
    <h3>grand Child Component</h3>
    <h4>Injected Data in grand child:{{ message }}</h4>
  </div>
</template>

<script lang="ts">
import { defineComponent, inject } from "vue";
import { ChildComponentData } from "./ChildComponentData";
import { ChildComponentKey } from "./ChildComponentKey";

export default defineComponent({
  name: "ChildComponent",
  setup() {
    // eslint-disable-next-line no-undef
    const data = inject<ChildComponentData>(ChildComponentKey);
    return { message: data?.message }; //composition
  },
});
</script>

<style></style>
