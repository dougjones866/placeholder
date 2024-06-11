<script setup>
import { ref } from 'vue'

const days = ref(["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"])
const selected = (day) => {
  console.log(day)
  selectedDay.value = day

}
const selectedDay = ref("")
</script>

<template>
  <h1>What is today?</h1>
  <ul>
    <li v-for="day in days" :key="day" @click="selected(day)">
      <p>{{ day }}</p>
    </li>
  </ul>
  <div class="todayIs">
    <h2>Today is <p class="selectedDay">{{ selectedDay }}</p>
    </h2>
  </div>
</template>


<style scoped>
ul {
  display: inline-flex;
  flex: wrap;
}

li {
  list-style: none;
  width: 100px;
  height: auto;
  text-align: center;
  padding: 5px;
}

p {
  background-color: green;
  padding: 10px;
  border: solid thin;
}

.selectedDay {
  text-align: center;
  width: 150px;
  background-color: green;
  padding: 5px;
  border: solid thin;
}

.todayIs {
  display: inline;
}
</style>
