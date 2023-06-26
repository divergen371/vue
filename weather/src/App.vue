<template>
  <Title />
  <Form />
  <button @click="getWeather">getWeatherのテスト</button>
</template>


<script setup>
import axios from "axios"
import Title from './Title.vue';
import Form from './Form.vue';

const getWeather = () => {
  axios.get("https://api.weatherapi.com/v1/current.json?key=94d8f656c4fc4ed8bf494411210307&q=London&aqi=no")
    .then(res => console.log(res))
}
</script>