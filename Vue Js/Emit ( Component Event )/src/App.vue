<script setup>

import ChildFormExample from './components/ChildFormExample.vue';
import { ref } from 'vue'
// const Form = (username, email, password) => {
//   console.log(username)
//   console.log(email)
//   console.log(password)
// }
const User = ref(null);

const handleUserInfo = (username, email, password) => {
  User.value = { username, email, password };
};

</script>

<template>
  <div class="main-section">

    <h4>Emit: Child to Parent..</h4>

    <div class="inner-section">
      <h1>Parent Component:</h1>
      <p>As you can see, we can access the child component's variables in the parent component, thanks to <b>$emit</b>.
      </p>

      <!-- You can directly call userInfo here , using Arrow function. Like Below 👇-->
      <!-- <ChildFormExample @userInfo="(username, email, password) => {
        console.log(username)
        console.log(email)
        console.log(password)
      }" /> -->

      <ChildFormExample @userInfo="handleUserInfo" />

      <!-- <div class="content" v-show="Form">
        <p>{{ Form.username }}</p>
        <p>{{ Form.email }}</p>
        <p>{{ Form.password }}</p>
      </div> -->

      <div class="content" v-if="User">
        <h2>User Details</h2>
        <p><strong>Username:</strong> {{ User.username }}</p>
        <p><strong>Email:</strong> {{ User.email }}</p>
        <p><strong>Password:</strong> {{ User.password }}</p>
      </div>
    </div>
  </div>

</template>

<!-- CSS -->
<style>
@import url('https://fonts.googleapis.com/css2?family=Fascinate+Inline&display=swap');

.main-section {
  background-color: rgb(250, 250, 234);
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.inner-section {
  border-radius: 10px;
  box-shadow: 0 0 10px black;
  border: 2px sold red;
  text-align: center;
  padding: 20px;
  background-color: rgb(231, 194, 93);
}

input {
  width: 100%;
  /* width: max-width(100%-40px); */
  box-sizing: border-box;
  padding: 20px;
  margin: 10px 0px;
  border: 1px solid black;
  border-radius: 8px;
  font-size: 16px;
  transition: border-color 0.3s ease;
}

button {
  font-size: 30px;
  padding: 10px 30px;
  border-radius: 10px;
  font-weight: 500;
}

button:hover {
  color: white;
  background-color: blue;
  border: 2px solid white;
  font-weight: 600;
}

h1 {
  font-family: "Fascinate Inline", system-ui;
  font-size: 40px;
}

p {
  font-size: 20px;
}

.content {
  margin-top: 20px;
  padding: 15px;
  border: 2px solid #333;
  border-radius: 10px;
  background-color: #fafafa;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.content h2 {
  margin-bottom: 10px;
}

.content p {
  font-size: 18px;
  color: #444;
}
</style>