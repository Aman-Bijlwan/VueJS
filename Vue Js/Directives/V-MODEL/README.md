# 🚀 Vue v-model Example App
This Vue application showcases the use of the `v-model` directive for two-way data binding between form inputs and reactive variables. It captures user inputs for `username`, `email`, and `password` and displays them in real-time.

## 🔧 Features
- Two-Way Data Binding: Real-time synchronization between input fields and Vue data model.
- Live Preview: Dynamically updates the displayed data as the user types.

## 📚 Code Explanation

**Vue Script**

```js
<script setup>
import { ref } from 'vue';
const Data = ref({ username: '', email: '', password: '' });
</script>
```
- `ref` is used to create reactive variables username, email, and password.
- `v-model` binds these inputs to the corresponding properties in the Data object.

**Template**
```html
<template>
  <div class="main">
    <h2>v-model Example:</h2>
    <input type="text" placeholder="Enter your name" v-model="Data.username" /><br>
    <input type="email" placeholder="Enter your email" v-model="Data.email" /><br>
    <input type="password" placeholder="Enter your password" v-model="Data.password" />
    <p>Username: {{ Data.username }}</p>
    <p>Email: {{ Data.email }}</p>
    <p>Password: {{ Data.password }}</p>
  </div>
</template>
```
- `v-model` provides two-way data binding between the form inputs and the Vue component’s state.
- As the user types in the input fields, the bound data updates in real-time.

## 💡 Real-Life Use Case: Stock Broker App
*Imagine a stock broker app where you input the amount you wish to invest. Using `v-model`, the app can dynamically update the number of stocks you can purchase based on the input amount, offering a responsive user experience.*



## Learn More
For more information about the `v-model` directive, visit the official Vue documentation [here](https://vuejs.org/guide/essentials/forms.html#v-model-basics).

****

****
> ***Feel free to explore and modify the code to see the power of v-model in action! 😊👍***
****

<!-- ### Final Output of this basic example:
![V-Model Example's UI](./src/assets/v-model%20example%20pic.png) -->
## 📸 Check Out the Final Output!
<img src="./src/assets/v-model%20example%20pic.png" alt="V-Model Example's UI" width="500" height="500" />