<!-- eslint-disable no-undef -->
<!-- eslint-disable vue/valid-template-root -->
<template>
  <div class="bg-warning">
    <h3>Child Component</h3>
    <h4>Injected Data:{{ message }}</h4>
    <GrandChild />
  </div>
</template>

<script lang="ts">
import { defineComponent, inject } from "vue";
import { ChildComponentData } from "./ChildComponentData";
import { ChildComponentKey } from "./ChildComponentKey";
import GrandChild from "./GrandChild.vue";

export default defineComponent({
  name: "ChildComponent",
  componets: { GrandChild },
  setup() {
    // eslint-disable-next-line no-undef
    const data = inject<ChildComponentData>(ChildComponentKey);
    return { message: data?.message }; //composition
  },
  components: { GrandChild },
});
</script>

<style></style>
