<script setup>
const Dynamic = defineProps(["f" ,'l'])
// const Last_Dynamic = defineProps([""])
// console.log(name)

</script>

<template>
       <div>
              <h3>Dynamic Props:</h3>
              <h1>{{ Dynamic.f }}  {{ Dynamic.l }}</h1>
       </div>
</template>