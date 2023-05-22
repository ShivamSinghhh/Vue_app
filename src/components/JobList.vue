<template>
  <div class="job-list">
    <h3 class="bg-primary">Sorted by {{ order }}</h3>
    <ul>
      <li v-for="job in sortedJobs" :key="job.id">
        <h2>{{ job.title }} in {{ job.location }}</h2>
        <div class="salary">
          <p>{{ job.salary }}</p>
        </div>
        <div class="note">
          <p>Here goes the note for the context ......</p>
        </div>
      </li>
    </ul>
  </div>
</template>
<script lang="ts">
import Job from "../types/Job";
import OrderTerm from "../types/OrderTerm";
import { defineComponent, PropType, computed } from "vue";
export default defineComponent({
  props: {
    jobs: {
      type: Array as PropType<Job[]>,
      required: true,
    },
    order: {
      type: String as PropType<OrderTerm>,
      required: true,
    },
  },
  setup(props: any) {
    console.log(` jobs :${props.jobs} - Sort on ${props.order}`);
    const sortedJobs = computed(() => {
      return [...props.jobs].sort((a: any, b: any) => {
        return a[props.order] > b[props.order] ? 1 : -1;
      });
    });
    return { sortedJobs };
  },
});
</script>
<style scoped>
.job-list {
  max-width: 960px;
  margin: 40px auto;
}
.job-list li {
  list-style-type: none;
  background: white;
  color: black;
  padding: 16px;
  margin: 16px 0;
  border-radius: 30px;
}
.job-list h2 {
  text-transform: capitalize;
}
.salary img {
  width: 30px;
}
.salary p {
  color: red;
  font-weight: bold;
  margin: 10px 4px;
}
.note {
  background: lightpink;
}
</style>
