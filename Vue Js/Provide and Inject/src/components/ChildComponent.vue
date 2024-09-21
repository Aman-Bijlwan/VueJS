<script setup>

import { inject } from 'vue';
const hlo = inject("client")


const myCrush = defineProps(['crush'])
</script>

<template>
       <div>
              <!-- <h2>Child Component:</h2> -->
              <h3>{{ myCrush.crush }}</h3>
              <h4>💘</h4>
              <h3>{{ hlo.name }}</h3>
       </div>
</template>