<script setup lang="ts">
import { ref, watch, onMounted } from 'vue'
import { motion } from 'motion-v'

const props = defineProps<{
  selectedTab: number | null
}>()

const nubRef = ref<HTMLElement | null>(null)
const left = ref(0)

const moveNub = () => {
  if (!props.selectedTab) return

  const hoveredTab = document.getElementById(`shift-tab-${props.selectedTab}`)
  const overlayContent = document.getElementById('overlay-content')

  if (!hoveredTab || !overlayContent) return

  const tabRect = hoveredTab.getBoundingClientRect()
  const contentRect = overlayContent.getBoundingClientRect()

  const tabCenter = tabRect.left + tabRect.width / 2 - contentRect.left
  left.value = tabCenter
}

onMounted(moveNub)
watch(() => props.selectedTab, moveNub)

</script>

<template>
  <motion.span ref="nubRef" :style="{ clipPath: 'polygon(0 0, 100% 0, 50% 50%, 0 100%)' }" :animate="{ left }"
    :transition="{ duration: 0.2, ease: 'easeOut' }"
    className="absolute left-1/2 top-0 h-4 w-4 -translate-x-1/2 -translate-y-1/2 rotate-45 rounded-tl border border-neutral-600 bg-neutral-900" />
</template>

<style scoped></style>
