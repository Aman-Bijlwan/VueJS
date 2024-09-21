<script setup>
import StaticProps from './components/StaticProps.vue'
import DynamicProps from './components/DynamicProps.vue'
import ChangePropValue from './components/ChangePropValue.vue'
import PropValidation from './components/PropValidation.vue'
import ComplexProps from './components/ComplexProps.vue'
import { ref } from 'vue'

const firstName = ref('Shifali')  
const lastName = ref('School')

</script>

<template>
  <div>

    <StaticProps something="Jordan" />
    <hr>
    <DynamicProps :f="firstName" :l="lastName" />
    <hr>
    <ChangePropValue :firstName="firstName" />
    <hr>
    <PropValidation firstName="Suman" :age=20 />
    <hr>
    <ComplexProps :clients="['John', 'Jessica', 'Aman']" :user="{ name:'Shifali',age:20}" />
    <hr>
  </div>
</template>