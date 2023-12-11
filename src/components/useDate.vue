<template>
  <div class="date-container">
    <p class="date-text">Current Date: {{ getCurrentDate() }}</p>
    <button @click="incrementDate" class="date-button">Increment Date</button>
    <button @click="decrementDate" class="date-button">Decrement Date</button>
  </div>
</template>

<script>
import { ref, } from "vue";

const useDate = (initialDate) => {
  const date = ref(initialDate);


  const getCurrentDate = () => {
    return date.value;
  };

  const addDays = (daysToAdd) => {
    const currentDate = date.value;
    const newDate = new Date(currentDate);
    newDate.setDate(newDate.getDate() + daysToAdd);
    date.value = newDate;
  };

  const addMonths = (monthsToAdd) => {
    const currentDate = date.value;
    const newDate = new Date(currentDate);
    newDate.setMonth(newDate.getMonth() + monthsToAdd);
    date.value = newDate;
  };

  return {
    getCurrentDate,
    addDays,
    addMonths,
   

  };
};

export default useDate;
</script> 

