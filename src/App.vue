<script setup lang="ts">
import { onMounted } from 'vue'
import { useAppStore } from '@/stores/app'

onMounted(() => {
  useAppStore().initTheme()
})
</script>

<template>
  <ScrollArea class="h-screen">
    <router-view v-slot="{ Component }">
      <transition name="fade" mode="out-in">
        <component :is="Component" />
      </transition>
    </router-view>
    <ScrollBar class="z-50" />
  </ScrollArea>
</template>
