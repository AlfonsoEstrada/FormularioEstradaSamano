<template>
  <div>
    <RouterLink :to="data.path">{{ data.name }}</RouterLink>
  </div>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router'
import type { IMenuItems } from '../../interfaces/IMenuItems'
const data = defineProps<IMenuItems>()
</script>
