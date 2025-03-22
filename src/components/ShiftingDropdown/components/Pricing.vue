<template>
  <div class="grid grid-cols-3 gap-4 divide-x divide-neutral-700">
    <a href="#"
      class="flex w-full flex-col items-center justify-center py-2 text-neutral-400 transition-colors hover:text-neutral-50">
      <Home :size="20" strokeWidth={1.5} class="mb-2 text-xl text-blue-500" />
      <span class="text-xs">Startup</span>
    </a>
    <a href="#"
      class="flex w-full flex-col items-center justify-center py-2 text-neutral-400 transition-colors hover:text-neutral-50">
      <BarChart :size="20" strokeWidth={1.5} class="mb-2 text-xl text-blue-500" />
      <span class="text-xs">Scaleup</span>
    </a>
    <a href="#"
      class="flex w-full flex-col items-center justify-center py-2 text-neutral-400 transition-colors hover:text-neutral-50">
      <PieChart :size="20" strokeWidth={1.5} class="mb-2 text-xl text-blue-500" />
      <span class="text-xs">Enterprise</span>
    </a>
  </div>
</template>

<script lang="ts" setup>
import { Home, BarChart, PieChart } from 'lucide-vue-next'
</script>