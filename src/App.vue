<template>
  <div class="app">
    <header>
      <div class="title">
        <img src="./assets/images/developer-icon.svg" alt="logo" />
        <h1>Developer Jobs</h1>
      </div>
      <div class="order">
        <button @click="handleClick('title')">Order by title</button>
        <button @click="handleClick('salary')">Order by salary</button>
        <button @click="handleClick('location')">Order by location</button>
      </div>
    </header>

    <JobsList :jobs="jobs" :order="order" />
  </div>
</template>

<script lang="ts" setup>
import { ref } from "vue";
import Job from "./types/Job";
import JobsList from "./components/JobsList.vue";
import { OrderTerm } from "./types/OrderTerm";

const jobs = ref<Job[]>([
  {
    title: "Full Stack Developer",
    location: "Amsterdam",
    salary: 60000,
    id: "1",
  },
  {
    title: "Front End Developer",
    location: "Rotterdam",
    salary: 55000,
    id: "2",
  },
  {
    title: "Back End Developer",
    location: "The Hague",
    salary: 58000,
    id: "3",
  },
  {
    title: "Mobile Developer",
    location: "Utrecht",
    salary: 50000,
    id: "4",
  },
  {
    title: "Data Scientist",
    location: "Eindhoven",
    salary: 65000,
    id: "5",
  },
  {
    title: "AI Engineer",
    location: "Tilburg",
    salary: 70000,
    id: "6",
  },
  {
    title: "Cloud Engineer",
    location: "Groningen",
    salary: 60000,
    id: "7",
  },
  {
    title: "DevOps Engineer",
    location: "Almere",
    salary: 55000,
    id: "8",
  },
  {
    title: "Software Tester",
    location: "Breda",
    salary: 45000,
    id: "9",
  },
  {
    title: "System Analyst",
    location: "Nijmegen",
    salary: 47500,
    id: "10",
  },
]);
const order = ref<OrderTerm>("title");

const handleClick = (term: OrderTerm) => {
  order.value = term;
};
</script>

<style lang="scss">
header {
  text-align: center;
  .order {
    margin-top: 20px;
  }
  .title {
    display: flex;
    justify-content: center;
  }
  img {
    width: 60px;
    margin-right: 20px;
  }
  h1 {
    font-size: 3em;
  }
}

button {
  margin: 0 10px;
  color: #1195c9;
  border: 3px solid #1195c9;
  background: #d5f0ff;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}
</style>
