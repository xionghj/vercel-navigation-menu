<script setup lang="ts">
import { ChevronDown } from 'lucide-vue-next'
defineProps<{
  selected: number | null
  tabId: number
  handleTabFocus: (val: number | null) => void
}>()

</script>

<template>
  <button :id="`shift-tab-${tabId}`" @click="handleTabFocus(tabId)" @mouseenter="handleTabFocus(tabId)"
    class="flex items-center gap-1 rounded-full px-3 py-1.5 text-sm transition-colors cursor-pointer" :class="{
      'bg-neutral-800 text-neutral-100': selected === tabId,
      'text-neutral-400': selected !== tabId
    }">
    <span>
      <slot></slot>
    </span>
    <ChevronDown class="transition-transform" :class="{ 'rotate-180': selected === tabId }" :size="20"
      :stroke-width="1.5"></ChevronDown>
  </button>
</template>

<style scoped></style>
