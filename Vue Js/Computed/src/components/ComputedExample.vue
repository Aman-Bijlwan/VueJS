<script setup>

import { computed, ref } from 'vue'

const count = ref(0)
const firtName = ref("")
const lastName = ref("")

//Computed is a special type of variable , that automatically updates itself , whenever data on which it depends changes.
const double = computed(() => {
  return count.value ** 2
})
//Increament 
const incre = () => count.value++


const fullName = computed(() => " ' " + firtName.value + " " + lastName.value + " ' ")

</script>

<template>
  <div>

    <h2>Computed Example 1:</h2>
    <h4>Original Number: {{ count }}</h4>
    <p>Double of Original Number: {{ double }}</p>
    <button
      @click="incre">Increament</button><!--@ is shorthand for v-on directive , that is used to bind eventListners-->
    <hr>
    <h2>Computed Example 2:</h2>
    <h4><input type="text" placeholder="Name:" v-model="firtName" /></h4>
    <!--V-model provides two way data binding , like here it is connecting this input field with firstName-->
    <h4><input type="text" placeholder="Name:" v-model="lastName" /></h4>
    <h3>Full Name: {{ fullName }}</h3>
  </div>

</template>