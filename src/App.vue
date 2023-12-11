 App.vue

<template>
  
    <div class="date-container">
    <p class="date-text">Current Date: {{ getCurrentDate() }}</p>
    <button @click="addDays(1)" class="date-button">Add1 Day</button>
    <button @click="addMonths(1)" class="date-button">Add 1 Month</button>
  </div>
</template>

<script>
import useDate from './components/useDate.vue';

export default {
  setup() {
    const { getCurrentDate, addDays, addMonths} = useDate(new Date());

    return {
      getCurrentDate,
      addDays,
      addMonths,
    };
  },
};
</script> 








<style >

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 270px;


 
}

.date-container {
  text-align: center;
  margin: 20px;


}

.date-text {
  font-size: 18px;
  margin-bottom: 10px;
}

.date-button {
  background-color: #4caf50;
  color: white;
  padding: 10px 20px;
  font-size: 16px;
  margin: 5px;
  cursor: pointer;
  border: none;
  border-radius: 5px;
}

.date-button:hover {
  background-color: #45a049;
}
</style>
