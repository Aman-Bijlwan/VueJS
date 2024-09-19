<script setup>
import { ref } from 'vue'
const Data = ref({ username: '', email: '', password: '' })
</script>

<template>
  <div class="background">
    <div class="main">
      <h2>v-model Example:</h2>

      <input type="text" placeholder="Enter your name" v-model="Data.username" /><br>
      <input type="email" placeholder="Enter your email" v-model="Data.email" /><br>
      <input type="password" placeholder="Enter your password" v-model="Data.password" />

      <p>Username: {{ Data.username }}</p>
      <p>Email: {{ Data.email }}</p>
      <p>Password: {{ Data.password }}</p>
    </div>
  </div>
</template>


<style scoped>

/* Importing Google fonts */
@import url('https://fonts.googleapis.com/css2?family=Fascinate+Inline&display=swap');

/* Background for full UI */
.background {
  background-color: #f0f4f8;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* Main container styling */
.main {
  box-shadow: 0px 0px 15px rgb(48, 135, 161);
  background-color: #fff;
  padding: 20px;
  border-radius: 10px;
  max-width: 400px;
  text-align: center;
}

/* Stylish input fields */
input {
  width: 100%;
  box-sizing: border-box;
  padding:20px;
  margin: 10px 0px;
  border: 1px solid black;
  border-radius: 8px;
  font-size: 16px;
  transition: border-color 0.3s ease;
}

/* Focus effect for input fields */
input:focus {
  border-color: #007bff;
  outline: none;
}

/* Stylish text */
h2 {

  color: #333;
  font-size: 34px;
  margin-bottom: 20px;
  font-family: "Fascinate Inline", system-ui;
  font-weight: 400;
  /* font-style: normal; */
}

/* Displayed data styling */
p {
  font-family: 'Courier New', Courier, monospace;
  font-size: 18px;
  color: #555;
}
</style>