<script setup lang="ts">
import { computed } from 'vue'
import { motion } from 'motion-v'
import Nub from './Nub.vue'
import Products from './Products.vue'
import Pricing from './Pricing.vue'
import Blog from './Blog.vue'
const TABS = [
  {
    title: 'Products',
    Component: Products,
  },
  {
    title: 'Pricing',
    Component: Pricing,
  },
  {
    title: 'Blog',
    Component: Blog,
  }
].map((tab, index) => {
  return {
    ...tab,
    id: index + 1
  }
})

const props = defineProps<{
  selectedTab: number
  direction: 'left' | 'right' | null
}>()


const x = computed(() => {
  return props.direction === "left" ? 100 : props.direction === "right" ? -100 : 0;
})
</script>

<template>
  <motion.div id="overlay-content"
    class="absolute left-0 top-[calc(100%_+_24px)] w-96 rounded-lg border border-neutral-700 bg-gradient-to-b from-neutral-950 via-neutral-900 to-neutral-900 p-4">
    <div class="absolute -top-[24px] left-0 right-0 h-[24px]" />
    <Nub :selected-tab="selectedTab" />
    <motion.div :initial="{ opacity: 0, y: 8 }" :animate="{ opacity: 1, y: 0 }" :exit="{ opacity: 0, y: 8 }">
      <div v-for="tab in TABS" :key="tab.id" class="overflow-hidden">
        <motion.div v-if="tab.id === selectedTab" :initial="{ opacity: 0, x: x }" :animate="{ opacity: 1, x: 0 }"
          :transition="{ duration: 0.2, ease: 'easeInOut' }">
          <component :is="tab.Component" class="transition-opacity" />
        </motion.div>
      </div>
    </motion.div>
  </motion.div>
</template>

<style scoped></style>
