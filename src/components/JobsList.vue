<template>
  <div class="job-list">
    <p>Ordered by {{ order }}</p>
    <ul>
      <li v-for="job in jobs" :key="job.id">
        <h2>{{ job.title }} in {{ job.location }}</h2>
        <div class="salary">
          <p>{{ job.salary }} dollars</p>
        </div>
        <div class="description">
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Deserunt
            quibusdam eius nesciunt, sunt ab sapiente magnam harum, eveniet
            facilis ad aliquid excepturi culpa a provident inventore, aut itaque
            numquam? Maiores!
          </p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script lang="ts" setup>
import { defineProps, PropType } from "vue";
import Job from "@/types/Job";
import { OrderTerm } from "@/types/OrderTerm";

const props = defineProps({
  jobs: {
    required: true,
    type: Array as PropType<Job[]>,
  },
  order: {
    required: true,
    type: String as PropType<OrderTerm>
  }
});
</script>

<style lang="scss" scoped>
.job-list {
  max-width: 960px;
  margin: 40px auto;

  ul {
    padding: 0;
  }

  li {
    list-style-type: none;
    background: white;
    padding: 16px;
    margin: 16px 0;
    border-radius: 6px;
  }

  h2 {
    margin: 0 0 10px;
    text-transform: capitalize;
  }
}

.salary {
  display: flex;
  img {
    width: 30px;
  }
  p {
    color: #17bf66;
    font-weight: bold;
    margin: 10px 4px;
  }
}
</style>
