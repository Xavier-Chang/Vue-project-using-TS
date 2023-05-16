<template>
  <div class="app">
    <p>{{ jobs[0].location}}</p>
  </div>
</template>

<script lang="ts" setup>
import { ref } from "vue";
import Job from "../types/Job";

const jobs = ref<Job[]>([
  { title: "Full Stack Developer", location: "ANP", salary: 3_500, id: "1948" },
  { title: "farm worker", location: "lon lon ranch", salary: 30000, id: "1" },
  { title: "quarryman", location: "death mountain", salary: 40000, id: "2" },
  { title: "flute player", location: "the lost woods", salary: 35000, id: "3" },
  { title: "fisherman", location: "lake hylia", salary: 21000, id: "4" },
  { title: "prison guard", location: "gerudo valley", salary: 32000, id: "5" },
]);
</script>

<style></style>
