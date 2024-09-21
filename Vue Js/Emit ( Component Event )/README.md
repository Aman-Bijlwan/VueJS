# 📘 Vue Component Event Example: $emit
>This project demonstrates how to use $emit in Vue to communicate between a child and parent component. 
>
>The app showcases a simple form in the child component, where users can enter their details.
>
>On form submission, the data is passed to the parent component, which displays the user's information.

##  🎯 Component Event ?

Component events are a <ins>way for `child components` to communicate with their `parent components`</ins>. 

They allow child components to *`emit`* events (custom events) that can be listened to and handled by their parent components.

## 📋 How It Works

***Child Component Emits an Event***

- Inside a child component, you can use the $emit method to trigger a custom event. This event can carry data that you want to send to the parent.

***Parent Component Listens to the Event***

- In the parent component's template, you can use the v-on directive (or the shorthand @) to listen for the custom event emitted by the child.


## 🚀 Features
- **`Parent-Child Communication`**: Passes data from the child component to the parent using $emit.
- **`Form Handling`**: The child component has a form with fields for username, email, and password.
- **`Dynamic Data Display`**: The parent component dynamically displays the form data upon submission.

## 🔗 How This App Works
### Child Component:

*1. <ins>Custom Event Creation</ins>*:

- `userInfo` is a custom event that we created. It carries the user details (username, email, password) as parameters.
- When the form is submitted, `$emit` triggers the userInfo event with these variables, sending them to the parent component.

```js
<form @submit.prevent="$emit('userInfo', username, email, password)">
    <input type="text" v-model="username">
    <input type="email" v-model="email">
    <input type="password" v-model="password">
    <button type="submit">Submit</button>
</form>
```

### Parent Component

*1. <ins>Event Listener Logic</ins>*:

- In the parent component, the `handleUserInfo` function is an event handler that listens to the `userInfo` event from the child component.
- The function captures the emitted variables <ins>`(username, email, password)`</ins> and assigns them to a reactive object called `User`.
- This makes it easy to use the received data within the parent component.

```js
const handleUserInfo = (username, email, password) => {
  User.value = { username, email, password };
};
```

*2. <ins>Display Logic</ins>*:

- The User object is reactive, meaning it updates whenever the data changes.
- The parent template uses `v-if` to conditionally render the user information once the User object is populated.

### Why {{ User.username }} and not just {{ User }}? 🤔

Vue automatically `"unwraps"` values when we use simple data types like strings, numbers, or arrays, meaning we can use just {{ User }} if User was a string or array.

However, `User` here is an `object`. Vue can't directly unwrap an object’s properties. That’s why we use User.username, which tells <ins>***Vue to access the username property inside the User object***</ins>.

```js
<div class="content" v-if="User">
    <h2>User Details</h2>
    <p><strong>Username:</strong> {{ User.username }}</p>
    <p><strong>Email:</strong> {{ User.email }}</p>
    <p><strong>Password:</strong> {{ User.password }}</p>
</div>
```

## 🔑 Key Concepts
1. ***`$emit`***: Used to send data from the child to the parent component.
2. ***`Custom Events`***: userInfo is a custom event defined by the developer to pass specific data from child to parent.
3. ***`Reactive Variables`***: Used to store and display data in the parent component.
4. ***`Event Handling`***: The parent listens for custom events and updates its state accordingly.

## 📝 Usage
Fill in the form fields in the child component.
Click "Submit" to see the data displayed in the parent component.

## Learn More
For more information about the `Component Event` directive, visit the official Vue documentation [here](https://vuejs.org/guide/components/events.html#component-events).


****
****

## 📸 Check Out the Final Output!
<img src="./src/assets/component Event.png" alt="Component Event" width=500 height=400/>
