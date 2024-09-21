<script setup>
const name = defineProps(["something"])
console.log(name)

</script>

<template>
       <div>
              <h3>Static Props:</h3>
              <h1>{{ name.something }}</h1>
       </div>
</template>