<script setup>
import { provide } from 'vue';
import ChildComponent from './components/ChildComponent.vue';
import SchoolComponent from './components/SchoolComponent.vue';

const user = {
  name: "Aman",
}

provide("client", user)


const Story = {
  name: "Aman",
  anotherName: "Anonymous"
}
//  If we want to send data using provide inject
provide("Name", Story)

// We can also send data directly into provide like :
// provide("Name", {
//   name: "Anonymous",
//   anotherName: "Aman"
// })

provide("Name", ["Anonymous","Aman"])

</script>

<template>
  <div>


    <h4>Provide and Inject: Advancement to Props..</h4>

    <SchoolComponent myName="Aman" herName="Hidden" />
    <!-- <SchoolComponent :myName="Story.name" :herName="Story.anotherName" /> -->

    <!-- <br>
    <br>
    <br>
    <br>
    <br>
    <fieldset>
      <legend>😉</legend>

      <ChildComponent crush="Aditi" />
    </fieldset> -->
  </div>
</template>
