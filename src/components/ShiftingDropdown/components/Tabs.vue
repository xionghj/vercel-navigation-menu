<script setup lang="ts">
import { AnimatePresence } from 'motion-v'
import { ref } from 'vue'
import Tab from './Tab.vue'
import Content from './Content.vue'
const TABS = [
  {
    title: 'Products',
  },
  {
    title: 'Pricing',
  },
  {
    title: 'Blog',
  }
].map((tab, index) => {
  return {
    ...tab,
    id: index + 1
  }
})

const selectedTab = ref<number | null>(null)
const direction = ref<'left' | 'right' | null>(null)

const handleTabFocus = (val: number | null) => {
  if (val === null) {
    direction.value = null
    selectedTab.value = null
    return
  }

  if (selectedTab.value !== null) {
    direction.value = selectedTab.value > val ? 'right' : 'left'
  }

  selectedTab.value = val
}
</script>

<template>
  <div @mouseleave="handleTabFocus(null)" class="relative flex h-fit gap-2">
    <Tab v-for="tab in TABS" :key="tab.id" :selected="selectedTab" :tab-id="tab.id" :handle-tab-focus="handleTabFocus">
      {{ tab.title }}
    </Tab>
    <template v-if="selectedTab">
      <AnimatePresence>
        <Content :direction="direction" :selectedTab="selectedTab" />
      </AnimatePresence>
    </template>
  </div>
</template>

<style scoped></style>
