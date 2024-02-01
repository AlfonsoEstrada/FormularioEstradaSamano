<script setup lang="ts">
import { RouterView } from 'vue-router'
import MenuComponent from './components/menu/MenuComponent.vue'
</script>

<template>
  <header>
    <MenuComponent></MenuComponent>
    <img src="../src/assets/logo.svg" alt="" srcset="" />
  </header>

  <RouterView />
</template>

<style>
nav {
  text-align: center;
  height: 100vh;
  width: 100%;
}
</style>
