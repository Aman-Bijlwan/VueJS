# 🚀 Vue Computed Property Example
This project demonstrates the use of computed properties in Vue. 
Computed properties are a special type of reactive property that automatically update themselves when the data they depend on changes. 🧠💡

*OR* 

A computed property is a special kind of variable that ***automatically updates*** itself , whenever the data it depends on changes.
- `It's like a little worker that watch certain data, performs some work on it, and always gives you the most up-to-date result.`


## 🛠️ Why Use Computed Properties?
Computed properties cache their results, meaning they only recalculate when the dependent data changes, making them more efficient for expensive operations compared to methods. 🏎️⚡

## 🔄 How Computed Properties Work:
> - **Caching in Computed Properties:**
Computed properties cache their values. If the dependent data hasn't changed, Vue returns the cached result, avoiding unnecessary recalculations.
>
>- **Triggering Mechanism:**
Vue automatically tracks which properties a computed property depends on and only updates when those properties change, optimizing performance.

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
- ***ref***: Creates reactive variables. 🌐
- ***computed***: Recalculates values based on changes in reactive data. 📊
- ***v-model***: Two-way binding between input fields and variables. 🔄

****
Feel free to explore the app and see how changes in the input fields dynamically update the displayed values! 😊👍
****