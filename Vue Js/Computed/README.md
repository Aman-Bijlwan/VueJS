# 🚀 Vue Computed Property Example
This project demonstrates the use of computed properties in Vue. computed properties are a special type of reactive property that automatically update themselves when the data they depend on changes. 🧠💡

## Why Use computed?
In Vue, while methods allow us to recalculate values when necessary, computed properties cache the result until the dependent data changes. This makes them more efficient for expensive operations. 🏎️⚡

## 📚 Example Overview
This Vue app provides a simple example to help you understand how computed properties work:

- Squaring a number: Simple number operations.
     -Dynamic full name generation: Using input fields for first and last names.
#### Example 1: Squaring a Number

```js
const count = ref(0)
const double = computed(() => count.value ** 2)
```
Here, double is calculated as the square of count. 🔢 Each time you increment count, double automatically updates! 📈

#### Example 2: Full Name Generation
```js
const firtName = ref("")
const lastName = ref("")
const fullName = computed(() => " ' " + firtName.value + " " + lastName.value + " ' ")
```
As the user types in the input fields, computed updates the full name in real time. ✍️👤


🔑 Key Concepts
ref: Creates reactive variables. 🌐
computed: Recalculates values based on changes in reactive data. 📊
v-model: Two-way binding between input fields and variables. 🔄