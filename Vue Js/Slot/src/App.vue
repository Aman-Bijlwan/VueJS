<script setup>
import BasicSlot from './components/BasicSlot.vue';
import FallbackSlot from './components/FallbackSlot.vue';
import NamedSlot from './components/NamedSlot.vue';
import DefaultSlot from './components/DefaultSlot.vue';

</script>

<template>
  <div>

    <h2><u>Basic Slot:</u></h2>
    <BasicSlot>
      <p><b>Content 1</b></p>
    </BasicSlot>
    <h5>Reusing Same Component with some different Content ( Where we have left some space using <b>"Slot"</b>) 👆👇</h5>
    <BasicSlot>
      <p><b>Content 2</b> </p>
    </BasicSlot>

    <hr>

    <h2><u>Fallback Slot:</u></h2>

    <FallbackSlot></FallbackSlot>

    <hr>

    <h2><u>Named Slot:</u></h2>

    <NamedSlot>
      <!-- For Named Slot , there are two method to initialize that :
      First , Using "v-slot" directive,
      Second : Using shorthand :-> "#" -->
      <template v-slot:First> <p>This content is assigned to <b>First Slot</b> in NamedSlot component</p></template>

      <template #Second> <p>This content is assigned to <b>Second Slot</b> in NamedSlot component</p></template>
    </NamedSlot>

    <hr>

    <h2><u>Default Slot:</u></h2>
    <DefaultSlot>
      <template #default>
        <p>This is <b>Default Slot's</b>  Content.</p>
      </template>
    </DefaultSlot>


  </div>
</template>