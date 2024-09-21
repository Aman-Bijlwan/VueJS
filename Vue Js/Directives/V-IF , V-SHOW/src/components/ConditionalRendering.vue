<script setup>
import { ref, onMounted } from 'vue'

const isTrue = ref(true)
const isFalse = ref(false)

const age = ref()

const show = ref("John")

const ask = () => {
  const userName = prompt("Enter your user name:")
  if (userName) {
    show.value = userName
    alert(`Your entered NAME i.e. " ${show.value} " will be shown in Example 3.`)
  }
}

onMounted(() =>
  ask()

)

</script>

<template>
  <div>
    <h4><u>There are various directives that fell under this concept :👇</u></h4>
    <dl>
      <dt><b>1. v-if:</b></dt>
      <dd>- <i>This is simple if condition , if its condition get's true , then its statement is printed.</i></dd><br>
      <dt><b>2. v-else-if:</b></dt>
      <dd>- <i>If if is not true , then this second statement is printed.</i></dd><br>
      <dt><b>3. v-else:</b></dt>
      <dd>- <i>If all are false , then this will print.</i> <u>{SIMPLE CONCEPTS , YOU ALREADY KNOW, but the way to
          initialize them is different}</u></dd><br>
      <dt><b>4. v-show:</b></dt>
      <dd>- <i>This will remove data if its condition is not meet , but unlike if -> it remove data entirely from dom .
          v-show removes data just from ui , and not entirly from DOM.</i> <u>{MEANS U CAN STILL SEE IT IN ELEMENTS IN
          INSPECT.} </u></dd>
    </dl>
    <hr>

    <h2>(I). Example 1:</h2>
    <h5 v-if="isTrue">isTrue is true.(v-if condition : success)</h5>
    <h5 v-else-if="isFalse">isFalse is true.(v-else-if condition: success)</h5>
    <h5 v-else>Nothing is true.</h5>
    <hr>

    <h2>(II). Example 2:</h2>
    <input type="text" placeholder="Enter your age here:" v-model="age" />
    <h5 v-if="age > 18">Success..</h5>
    <h5 v-else-if="age >= 14 && age <= 18">Wait</h5>
    <h5 v-else>Failed</h5>
    <hr>

    <h2>(III). Example 3:</h2>
    <h4># v-show Directive:</h4>
    <h5 v-show="show">Name: {{ show }}</h5>
    <p>
      <i>"I've used an h5 tag above this p element to display a name, and the v-show directive has been applied. As a
        result, the name is not visible because I set the condition to !show (which means show is false).
        <br> You can observe that the name isn't displayed in the UI, but you can still see the element in the browser's
        inspect tool."
      </i>
    </p>

  </div>
</template>