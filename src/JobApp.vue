<template>
  <div class="bg-dark text-warning">
    <header>
      <div class="order text-center bg-success">
        <button @click="handleClick('title')">Sort by title</button>&nbsp;
        <button @click="handleClick('salary')">Sort by salary</button>&nbsp;
        <button @click="handleClick('location')">Sort by location</button>
      </div>
    </header>
    <JobList :jobs="jobs" :order="order" />
  </div>

  <!-- <div class="d-flex justify-content-evenly bg-dark text-warning">
    <div class="p-2">ID</div>
    <div class="p-2">Title</div>
    <div class="p-2">salary</div>
    <div class="p-2">Location</div>
  </div>

  <div
    class="d-flex justify-content-evenly border border-info"
    v-for="(item, id) in jobs"
    :key="id"
  >
    <div class="p-2">{{ item.id }}</div>
    <div class="p-2">{{ item.title }}</div>
    <div class="p-2">{{ item.salary }}</div>
    <div class="p-2">{{ item.location }}</div>
  </div> -->
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs, ref } from "vue";
import Job from "./types/Job";
import JobList from "./components/JobList.vue";
import OrderTerm from "./types/OrderTerm";

// composition API - code is simple/elegant/readable
export default defineComponent({
  name: "JobApp",
  components: { JobList },
  setup() {
    const jobs = ref<Job[]>([
      { id: "101", title: "Analyst", location: "Bengaluru", salary: 45000 },
      { id: "102", title: "Sr Analyst", location: "Chhenai", salary: 55000 },
      {
        id: "103",
        title: "Associate Consultant",
        location: "Delhi",
        salary: 65000,
      },
      { id: "104", title: "Consultant", location: "Hyderabad", salary: 75000 },
      {
        id: "105",
        title: "Sr Consultant",
        location: "Pune",
        salary: 85000,
      },
    ]);
    const order = ref<OrderTerm>("title");
    const handleClick = (term: OrderTerm) => {
      order.value = term;
    };
    return { jobs, order, handleClick };
  },
  // automatically invoked at the time of creation of app
  // const name = "shivam";
  // const salary = 65000;
  // const state = reactive({
  //   name: "shivam" as string,
  //   salary: 65000 as number | string,
  // });
  // return { ...toRefs(state) };

  methods: {
    // changeName(ename: string) {
    //   this.name = ename;
    //   return ename;
    // },
    // changeSalary(salary: number | string) {
    //   this.salary = salary;
    //   return salary;
    // },
  },
});
</script>

<style scoped>
header {
  text-align: center;
}
</style>
