<script setup>
// const Validation = defineProps(["firstName", 'age'])

// 😉😉BASIC VALIDATION:
// const Validation = defineProps({
//        firstName: String,
//        age: Number
// })

// Now , if we assign number to firstName and string to age,  it will work fine in ui , but will give error in console, i.e. 
// ""[Vue warn]: Invalid prop: type check failed for prop "firstName". Expected String with value "20", got Number with value 20. 
//   at <PropValidation firstName=20 age="Suman" > 
//   at <App>""

// and same for age 
// because we have validate String to firstName , and Number to age , So on replacing that we received that error ,


// 😉😉COMPLEX VALIDATION:
const Validation = defineProps({
       firstName: {
              type: String,
              Required: true,
              default: "Anonymous"

       },
       age: Number
})


</script>

<template>
       <div>
              <h3>Prop Validation:</h3>
              <h1>{{ Validation.firstName }} {{ Validation.age }}</h1>
       </div>
</template>