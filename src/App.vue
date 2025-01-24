<template>
  <div class="wrapper">
    <div class="app-container">
      <HeaderComponent />
      <router-view />
    </div>
  </div>
</template>
<script setup>
import HeaderComponent from "./components/HeaderComponent.vue";
</script>

<style lang="scss">
@use "./assets/styles/common-styles/container.scss" as *;
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  color: #2c3e50;
}
.app-container {
  //padding: 10px 20px;
}
nav {
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 20px;
  padding: 30px;

  a {
    //font-weight: bold;
    // color: #2c3e50;

    &.router-link-exact-active {
      color: $secondaryColor;
    }
  }
}
</style>
