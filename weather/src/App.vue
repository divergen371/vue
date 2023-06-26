<template>
  <Title />
  <Form @submit-form="getWeather" />
  <Results :results="results" />
</template>


<script setup>
import { reactive } from "vue";
import axios from "axios"
import Title from './Title.vue';
import Form from './Form.vue';
import Results from "./Results.vue";

const results = reactive({
  country: "",
  cityName: "",
  temperature: "",
  conditionText: "",
  icon: ""
})

const getWeather = (city) => {
  axios.get(`https://api.weatherapi.com/v1/current.json?key=94d8f656c4fc4ed8bf494411210307&q=${city}&aqi=no`)
    .then(res => {
      results.country = res.data.location.country,
        results.cityName = res.data.location.name,
        results.temperature = res.data.current.temp_c,
        results.conditionText = res.data.current.condition.text,
        results.icon = res.data.current.condition.icon
    })
}
</script>