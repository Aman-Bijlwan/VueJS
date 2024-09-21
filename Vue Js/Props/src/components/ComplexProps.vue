<script setup>

defineProps({
       clients: Array,
       user: Object
})

// 🙄We can also do it like the below , as in all previous props.$props
// But if we need to enable for loop on it , then we need to tell for loop to take person from complex.clients, and same for user.
// const complex = defineProps({
//        clients: Array,
//        user: Object
// })

</script>

<template>
       <div>
              <h2>Complex Props:</h2>
              <h1>{{ clients }}</h1>
              <h1>{{ user }}</h1>

              <ul v-for="(person, index ) in clients" :key="index">
                     <li>{{ person }}</li>
              </ul>

              <ul v-for="( u, i ) in user" :key="i">
                     <li>{{ u }}</li>
              </ul>
       </div>
</template>