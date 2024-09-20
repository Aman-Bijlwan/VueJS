<!-- v-for Directive is used to iterate over the arrays, object , and create a template for each item in collection -->

<script setup>
import { ref } from 'vue'
// let people = ref(['Hi', 'Hello', 'Bye'])

let books = ref([
  {
    id: 1,
    name: "Harry Potter",
    author: "JK Rowlings"
  },
  {
    id: 2,
    name: "Iron Man",
    author: "Stan Lee"
  }

])

</script>

<template>
  <!-- <p v-for="( person, index ) in people" :key="index">{{ person }}</p> -->
  <div>
    <p v-for="(content, index) in books" :="content.id">{{ content }}</p>
  </div>

</template>