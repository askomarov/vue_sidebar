<script setup>
import Sidebar from "./components/Sidebar.vue";
</script>

<template>
  <div class="app">
    <Sidebar></Sidebar>
    <router-view />
  </div>
</template>

<style lang="scss">
:root {
  --primary: #4ade80;
  --sidebar-width: 300px;
  --dark: #473a3a;
  --light: #c3c3c3;
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
button {
  cursor: pointer;
  appearance: none;
  border: none;
  outline: none;
  background: none;
}
.app {
  display: flex;
  main {
    flex: 1 1 0;
    padding: 1rem;
    @media (max-width: 768px) {
      padding-left: 6rem;
    }
  }
}
</style>
