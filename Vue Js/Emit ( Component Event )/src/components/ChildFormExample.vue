<script setup>
import { ref } from 'vue'

const username = ref('')
const email = ref('')
const password = ref('')
</script>

<template>
       <div class="main">

              <form @submit.prevent="$emit('userInfo', username, email, password)">
                     <input type="text" placeholder="Enter your Name:" name="username" v-model="username"><br>
                     <input type="email" placeholder="Enter your Email:" name="email" v-model="email"><br>
                     <input type="password" placeholder="Enter your Password:" name="password" v-model="password"><br>
                     <button type="submit">Submit</button>
              </form>

       </div>

</template>


<!-- <style scoped>

</style> -->