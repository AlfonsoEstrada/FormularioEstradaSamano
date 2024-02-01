<template>
  <div>
    <MenuItem
      class="Menu"
      v-for="route in routerViews"
      :name="route.name"
      :path="route.path"
      :key="route.name"
    ></MenuItem>
  </div>
</template>

<style>
.Menu {
  display: grid;
  grid-template-columns: 3fr 3fr 3fr;
  justify-content: center;
  align-items: center;
  height: 100%;
  width: 100%;
}
</style>

<script lang="ts" setup>
import MenuItem from './MenuItem.vue'
import router from '@/router/index'
import { type IMenuItems } from '@/interfaces/IMenuItems'

const routerViews = router.options.routes.filter((route) => {
  return route
}) as IMenuItems[]
</script>
