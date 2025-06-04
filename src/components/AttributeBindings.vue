<script setup>
import { ref } from 'vue'
import PageTitle from '../components/PageTitle.vue'
const titleClass = ref('title')
</script>

<template>
  <h1 :class="titleClass">Make me red</h1>
</template>

<style>
.title {
  color: red;
}
</style>