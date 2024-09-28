# 📘 Vue.js Template Refs
***`Template Refs`*** `(short for references)` provide a way to directly access DOM elements or child components within your Vue.js templates. This feature is particularly useful when you need to interact with or manipulate DOM elements in a more direct way, beyond what Vue’s declarative rendering can achieve.

## 🚀 Why Use Template Refs?
Template refs allow you to:

- Directly access and manipulate DOM elements.
- Interact with child component instances.
- Perform actions like focusing an input or modifying an element’s style.

## 🛠️ How to Use Template Refs?
1. **Basic Ref Usage**: You can create a reference to a DOM element by adding the ref attribute to it. Then, you can access this element in your JavaScript code using the ref object.

2. **Function Refs:** Instead of using a static ref attribute, you can use a function ref to perform more complex operations when an element is rendered or updated.

3. **Component Refs:** Use refs to access and interact with child component instances. This is useful for calling methods or accessing data exposed by child components.

## 📚 Understanding the Examples:
### 1. Basic Ref
Component: `BasicRef.vue`

- **Explanation**: This example demonstrates how to create a basic template ref to access and manipulate a DOM element. The input field gains focus, and its value is set programmatically.
- **Use Case**: Useful for cases where direct manipulation of the DOM element is required, such as setting focus or modifying properties.

```HTML       
<input type="text" placeholder="Enter Your Name" ref="myRef" />
```
JavaScript Logic:

```js
onMounted(() => {
  myRef.value.focus();
  myRef.value.value = 'something';
});
```
### 2. Function Ref
Component: `FunctionRef.vue`

- **Explanation**: Instead of a static ref, a function ref is used to perform operations directly on the element. This example changes the text content and style of an element using a function reference.
- **Use Case:** Ideal for complex interactions where a standard ref is not sufficient.

```html
<h1 :ref="myRefFunc">This is initial value</h1>
```
JavaScript Logic:

```js
const myRefFunc = (el) => {
  el.textContent = 'Text Changed';
  el.style.color = 'red';
};
```

### 3. Component Ref
Component: `RefComponent.vue` with `MyComponent.vue`

- **Explanation:** This example demonstrates how to reference a child component and access its methods and data using the ref attribute. The defineExpose method is used to expose data and methods to the parent.
- **Use Case:** Useful when you need to directly interact with child components, such as calling their methods or accessing their internal state.

```html
<MyComponent ref="myRef" />
```
JavaScript Logic in Child Component (MyComponent.vue):

```js 
defineExpose({ count, increment, decrement });
```
### 4. Watchers with Refs
Component: `RefWithWatch.vue`

- **Explanation:** This example shows how to use a watcher to monitor changes to a template ref. It logs messages and performs actions when the ref is updated or unmounted.
- **Use Case:** Suitable for scenarios where you need to react to changes in the DOM element or handle cases where elements are dynamically added or removed.

```js
watchEffect(() => {
  if (inputRef.value) {
    inputRef.value.focus();
  }
});
```
## 🔍 Key Differences Between v-if and v-show with Refs:
- **`v-if`**: Completely removes the element from the DOM if the condition is false, making the ref null.
- **`v-show`**: Only hides the element from view but keeps it in the DOM, allowing the ref to retain its reference.

For instance, if you need to keep a ref active for operations but hide the element conditionally, v-show is the right choice. Otherwise, if you need to remove the element entirely, use v-if.

## 🔗 Why Use Template Refs?
- **Direct DOM Access:** Sometimes you need to perform actions on an element that Vue’s declarative rendering can’t handle, such as manipulating focus or reading specific properties.
- **Accessing Child Components:** You may want to call methods or access data from child components directly, which is possible using component refs.
## 📄 Official Documentation
For more detailed information about template refs, check out the Vue.js [Template Refs Documentation](https://vuejs.org/guide/essentials/template-refs.html#template-refs).