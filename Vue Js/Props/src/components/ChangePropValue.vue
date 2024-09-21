<!-- We cannot change props value.  Props are immutable. -->

<script setup>
const Dynamic = defineProps(["firstName", 'lastName'])
// const Last_Dynamic = defineProps([""])
// console.log(name)

// Dynamic.firstName = "Suman" //❌❌ we cannot do this , as props have a behaviour of readonly, 
//💀💀Error we get in console: "[Vue warn] Set operation on key "firstName" failed: target is readonly. P"

//It will still print , the name given to firstName in this file, and will show an error in console.

</script>

<template>
       <div>
              <h3>(III) Props are immutable:</h3>
              <h1>{{ Dynamic.firstName }}</h1>
       </div>
</template>