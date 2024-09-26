<script setup>
// Import the 'ref' function from Vue to create reactive references
import { ref } from 'vue';

// radius
const radius = ref(100);

// mouse position constants
const mouseX = ref(0);
const mouseY = ref(0);
const isMenuShown = ref(false);

// Function to show an alert
function showAlert() {
  alert('HEY');
}

// Function to handle click and display the menu
function handleClick(event) {
  mouseX.value = event.clientX;
  mouseY.value = event.clientY;
  isMenuShown.value = true; // Update the reactive value correctly
}
</script>

<template>
  <!-- This div covers the whole screen and listens for click events -->
  <div @click="handleClick" id="wholeScreen">
    <!-- Buttom button-->
    <div
      v-if="isMenuShown"
      id="button"
      :style="{
        top: mouseY + 75 + 'px',
        left: mouseX - 25 + 'px',
      }"
    ></div>

    <!-- Top button -->
    <div
      v-if="isMenuShown"
      id="button"
      :style="{
        top: mouseY - 125 + 'px',
        left: mouseX - 25 + 'px',
      }"
    ></div>

    <!-- Right button -->
    <div
      v-if="isMenuShown"
      id="button"
      :style="{
        top: mouseY - 25 + 'px',
        left: mouseX + 75 + 'px',
      }"
    ></div>

    <!-- Left botton-->
    <div
      v-if="isMenuShown"
      id="button"
      :style="{
        top: mouseY - 25 + 'px',
        left: mouseX - 125 + 'px',
      }"
    ></div>
  </div>
</template>

<style>
#wholeScreen {
  width: 100vw;
  height: 100vh;
}

#button {
  position: absolute;
  border-radius: 50%;
  width: 70px;
  height: 70px;
  background-color: blue;
}
</style>
