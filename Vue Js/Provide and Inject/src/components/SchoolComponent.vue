<script setup>
import StudentComponent from './StudentComponent.vue';

// If we use props , then first variable is send to this component , then StudentComponent
defineProps(['myName','herName'])

//But if we use provide , then we can directly use inject in the StudentComponent and can directly access data there from App.vue
// So , no need to come here 

</script>

<template>
       <StudentComponent :myName="myName" :herName="herName"/>
</template>