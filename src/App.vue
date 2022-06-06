<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import Home from './pages/Home.vue'
</script>

<template>
  <Home />
</template>

<style>
html {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  -webkit-box-sizing: inherit;
  -moz-box-sizing: inherit;
  box-sizing: inherit;
}

body {
  min-height: 100vh;
  display: flex;
  flex-flow: column nowrap;
  justify-content: center;
  align-content: center;
  align-items: center;

  background:
    url('assets/img/gold_background.jpg') left bottom no-repeat,
    url('assets/img/gold_background.jpg') right top no-repeat;
  background-size: 70%, 30%;
  background-color: #060507;

}

html,
body {
  font-size: 16px;
}
</style>
