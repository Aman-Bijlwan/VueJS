<script setup>

import { inject } from 'vue';
//If we accept data as prop from SchoolComponent👇:
defineProps(['myName', 'herName'])


//If we accept data as provide , inject from App.vue👇:
const client = inject("Name")

</script>

<template>
       <div>
              <h2>Student Component</h2>
              
              <h3>{{ myName }} {{ herName }}</h3>
              <h3>{{client }}</h3>

       </div>
</template>
