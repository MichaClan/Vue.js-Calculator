<template>
  <div>
    <p>{{ display }}</p>
  </div>
</template>

<script setup>
/* eslint-disable */
import { ref } from 'vue'

const eersteGetal = ref(0)
const tweedeGetal = ref(0)
const resultaat = ref(0)
const operator = ref(null)
const display = ref("0")
</script>

<style>
</style>