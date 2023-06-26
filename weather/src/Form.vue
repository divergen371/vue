<template>
    <form action="">
        <input type="text" name="" id="" v-model="city" placeholder="都市名を英語で入力">
        {{ city }}
        <button>Get Weather</button>
    </form>
</template>

<script setup>
import { ref } from 'vue';
const city = ref("")
</script>
