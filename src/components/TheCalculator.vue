<template>
  <div>
    <p>{{ display }}</p>
    <button @click="drukOpCijfer('1')">1</button>
    <button @click="drukOpCijfer('2')">2</button>
    <button @click="drukOpCijfer('3')">3</button>
    <button @click="drukOpOperator('+')">+</button>
    <button @click="drukOpOperator('-')">-</button>
    <button @click="drukOpOperator('*')">×</button>
    <button @click="drukOpOperator('/')">÷</button>
    <button @click="berekenen()">=</button>
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

function drukOpCijfer(cijfer) {
  if (display.value === "0") {
    display.value = cijfer
  } else {
    display.value = display.value + cijfer
  }
}

function drukOpOperator(gekozenOperator) {
  eersteGetal.value = display.value
  operator.value = gekozenOperator
  display.value = 0
}

function berekenen() {
  const a = Number(eersteGetal.value)
  tweedeGetal.value = display.value
  const b = Number(tweedeGetal.value)

  if (operator.value === "+") {
    resultaat.value = a + b
  } else if (operator.value === "-") {
    resultaat.value = a - b
  } else if (operator.value === "*") {
    resultaat.value = a * b
  } else if (operator.value === "/") {
    resultaat.value = a / b
  }
  display.value = resultaat.value
}

function reset(){
  resultaat.value = 0
  operator.value = null
  display.value = "0"
  eersteGetal.value = 0
  tweedeGetal.value = 0
}
</script>

<style></style>