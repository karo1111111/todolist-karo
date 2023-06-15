<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
<div class="catsandstars">
  

    <div class="center-container">
    <div class="containers">
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="205" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </div>
  </div>
</div>
</template>

<style>
.containers {

  background: rgba(177, 225, 228,0.6);
  display: flex;
  justify-content: center;
}

.center-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
}


.catsandstars {
  background-image: url("./tech.jpeg");
  background-size: cover;
  background-position: center;
  background-color: transparent;
  width: 100vw;
  height: 100vh;
}

</style>