# 🌀 Vue Lifecycle Hooks Example
This project demonstrates the use of Vue.js Lifecycle Hooks. Lifecycle hooks are special functions provided by Vue to let you perform actions at different stages of a component's lifecycle. This helps in managing the state, side-effects, and DOM interactions effectively.

## 📜 What are Lifecycle Hooks?
Lifecycle hooks allow you to add logic at specific points in a component's lifecycle. Think of them as checkpoints or stages in the lifecycle of a component where you can run specific code.

### Lifecycle Stages:
1. **Mounting**: When a component is being created and inserted into the DOM.
2. **Updating**: When the reactive state of a component changes and the component re-renders.
3. **Unmounting**: When a component is being removed from the DOM.
### Why Use Lifecycle Hooks?
- `Mounting Hooks` can be used for actions like fetching data or setting up subscriptions.
- `Updating Hooks` help manage side effects or compare previous and current state.
- `Unmounting Hooks` are essential for cleanup tasks such as removing event listeners or canceling API requests.
## 🚀 Key Lifecycle Hooks Explained

### 1. onBeforeMount
Called right before the component is mounted. At this point, the component's state and data are set up, but the DOM is not rendered yet.

### 2. onMounted
Triggered after the component has been added to the DOM. This is ideal for initializing third-party libraries, making API calls, or setting up event listeners.

### 3. onBeforeUpdate
Executed just before the component re-renders due to a state change. Use this to capture the state before it changes or to perform operations that depend on the pre-updated state.

### 4. onUpdated
Called after the component has updated in the DOM. It is useful for performing actions based on the updated DOM state.

### 5. onBeforeUnmount
Runs before a component is destroyed and removed from the DOM. Use this hook for pre-cleanup, like saving user input or triggering alerts.

### 6. onUnmounted
Triggered once a component is completely removed from the DOM. Use this for final cleanup, such as removing timers or subscriptions.

## 📝 Understanding the Example
In this example, we have a component that demonstrates the use of all lifecycle hooks by logging messages at each stage. The component updates its message and unmounts itself based on button clicks, illustrating the flow of these hooks in action.

### Example Overview:
1. <ins>**`Component Mounting`**</ins>:

    The component logs messages when it is about to be mounted and after it has been mounted.
2. <ins>**`Component Updating`**</ins>:

   It logs messages when the state is about to change and after the state has changed.
3. <ins>**`Component Unmounting`**</ins>:

   It logs messages before and after the component is removed from the DOM.


The example shows how these hooks are triggered at each stage and allows you to see the component’s lifecycle in action through log messages in the console.

## 🔑 Key Concepts:

1. **Mounting**: Setup initial data, fetch resources.
2. **Updating**: Compare states, manage side effects.
3. **Unmounting**: Cleanup resources, remove listeners.

## 🌟 Why Lifecycle Hooks?
Lifecycle hooks are crucial for managing component behavior at different stages. They allow for optimal resource management, reduce memory leaks, and help maintain clean code structure.


## 🔗 Further Reading
For more detailed information, refer to the [Vue.js Lifecycle Hooks Documentation](https://vuejs.org/api/composition-api-lifecycle.html#composition-api-lifecycle-hooks).