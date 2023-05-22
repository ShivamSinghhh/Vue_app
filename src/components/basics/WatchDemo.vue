<template>
  <div class="bg-warning">
    <h2>{{ myValue }}</h2>
    search:<input type="text" v-model="myValue" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, watch } from "vue";

export default defineComponent({
  name: "WatchDemo",
  setup() {
    const myValue = ref("Shivam");
    watch(
      myValue,
      (newValue, oldValue) => {
        // fetch(url+newValue).then(resp= result.value = resp.data)
        console.log(`myValue changed to ${newValue} from ${oldValue}`);
      },
      { immediate: true } // eager watch
      // watchEffect() track all ref dependencies old value will not be there.
    );
    return { myValue };
  },
});
</script>

<style></style>
