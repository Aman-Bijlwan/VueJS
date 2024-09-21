# 🛠️ Vue Props Example
This project demonstrates various concepts and use cases for props in Vue.js, including static and dynamic props, prop immutability, validation, and handling complex props. Props are a fundamental way to pass data between components in Vue, allowing you to build reusable and dynamic applications.

## 📜 What are Props?
Props (short for "properties") are custom attributes that can be passed from a parent component to a child component. They allow data to be transferred in a unidirectional flow, helping to create dynamic components. Props are primarily used for:

- Sharing data between components.
- Creating reusable and modular components.
- Establishing communication between parent and child components.
## 🔄 Why Use Props?
Props facilitate component-based development by allowing parent components to pass data and configurations to their child components. This enables components to be more dynamic and adaptable based on the provided props. Props also help to maintain a clear data flow, which is crucial for predictable state management.

## 📌 Types of Props: Static & Dynamic
Props can be categorized into two main types:

### 1. Static Props
- **Definition**: Static props are fixed values passed directly from the parent component to the child. They don't change after being set, making them ideal for constants like labels or initial values.
- **Example Use Case**: Passing a fixed label like "Submit" or a heading title to a child component.
- Example in Code:

```js 
<!-- Parent Component -->
<StaticProps something="Hello, World!" />

<!-- Child Component: StaticProps.vue -->
<template>
  <div>
    <h1>{{ something }}</h1>
  </div>
</template>

<script setup>
const props = defineProps(['something'])
</script>
```

Here, the something prop is a static string passed to the child component.

### 2. Dynamic Props
- **Definition**: Dynamic props receive values that can change over time based on user actions or state changes. These values are often reactive variables, allowing the child component to automatically update whenever the parent data changes.
- **Example Use Case**: Displaying a user’s current status or profile information that can change based on user interactions.
- Example in Code:

```js 
<!-- Parent Component -->
<DynamicProps :f="firstName" :l="lastName" />

<!-- Child Component: DynamicProps.vue -->
<template>
  <div>
    <h1>{{ f }} {{ l }}</h1>
  </div>
</template>

<script setup>
const props = defineProps(['f', 'l'])
</script>
```
In this example, f and l are dynamic props representing firstName and lastName values that can change.

## 🔒 Prop Immutability
### What is Prop Immutability?
Props in Vue are immutable, meaning they cannot be directly modified inside the child component. This ensures a one-way data flow, maintaining the integrity of the data passed from parent to child.

### Why is This Important?
Immutable props prevent accidental modifications in child components, keeping the data flow predictable and consistent.

### Example Use Case:
When you want to display read-only data like user profile information or configuration settings that should not be altered by the child component.

```js 
<!-- Parent Component -->
<ChangePropValue :firstName="firstName" />

<!-- Child Component: ChangePropValue.vue -->
<template>
  <div>
    <h1>{{ firstName }}</h1>
    <!-- Attempting to modify the prop value directly will throw an error -->
    <!-- firstName = "New Name" ❌❌ Cannot do this -->
  </div>
</template>

<script setup>
const props = defineProps(['firstName'])
// props.firstName = "New Name" // ❌ This will throw an error
</script>
```
This demonstrates that modifying firstName directly within the child component will result in an error, reinforcing the immutability of props.

## ✅ Prop Validation
### What is Prop Validation?
Prop validation is a way to ensure that the data being passed to a component meets specific requirements. You can define the expected data type, whether the prop is required, and provide default values.

### Why Use Prop Validation?
It helps catch errors early by ensuring that components receive the correct type of data. This makes your components more robust and easier to debug.

### Example Use Case:
When a component expects a specific data type, such as a String for a name or a Number for an age, and should notify the developer if incorrect data is passed.

```js
<!-- Parent Component -->
<PropValidation firstName="John" :age="25" />

<!-- Child Component: PropValidation.vue -->
<template>
  <div>
    <h1>{{ firstName }} - {{ age }}</h1>
  </div>
</template>

<script setup>
const props = defineProps({
  firstName: {
    type: String,
    required: true,
    default: "Unknown"
  },
  age: {
    type: Number,
    required: true
  }
})
</script>
```
Here, if age is passed as a String instead of a Number, Vue will throw a warning, helping you catch potential issues early.

## 🔄 Complex Props: Arrays & Objects
### What are Complex Props?
Complex props involve passing arrays, objects, or other nested data structures from the parent to the child component. They allow the child to process and render more detailed data structures.

### Why Use Complex Props?
They enable child components to handle and display structured data like lists or nested objects, making the component logic cleaner and more maintainable.

### Example Use Case:
Passing an array of user objects or a single user profile object to a component that will display each user’s information.

```js
<!-- Parent Component -->
<ComplexProps :clients="['John', 'Jessica', 'Aman']" :user="{ name: 'Shifali', age: 20 }" />

<!-- Child Component: ComplexProps.vue -->
<template>
  <div>
    <h2>Clients List:</h2>
    <ul v-for="(client, index) in clients" :key="index">
      <li>{{ client }}</li>
    </ul>
    <h2>User Info:</h2>
    <ul>
      <li>Name: {{ user.name }}</li>
      <li>Age: {{ user.age }}</li>
    </ul>
  </div>
</template>

<script setup>
const props = defineProps({
  clients: Array,
  user: Object
})
</script>
```
In this example, clients is an array of names, and user is an object containing detailed information. This allows the child component to display complex data easily.


## 🛠️ Example:
Consider a User Information Dashboard where each component displays different user details:

1. **`Static Props`**: Display static user role or status.
2. **`Dynamic Props`**: Show real-time updates of user activities.
3. **`Complex Props`**: Display detailed user profiles or lists of recent activities.
Using props keeps the data flow clear and predictable, which is crucial for managing complex UI states.

## 🔑 Key Concepts
1. **Props as Read-only**: Props should not be modified in child components.
2. **Unidirectional Data Flow**: Data flows from parent to child components, ensuring a predictable state.
3. **Validation and Default Values**: Props can be validated for data type and required status, and they can have default values.

## 🔗 Learn More
For more details on Vue props, visit the official Vue documentation: [Vue.js Props](https://vuejs.org/guide/components/props.html#props).