<template>
  <div>
    <div class="grid grid-cols-2 gap-2">
      <a href="#">
        <img class="mb-2 h-14 w-full rounded object-cover" src="https://avatars.githubusercontent.com/u/26369276?v=4"
          alt="Placeholder image" />
        <h4 class="mb-0.5 text-sm font-medium">Lorem ipsum dolor</h4>
        <p class="text-xs text-neutral-400">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Amet illo
          quidem eos.
        </p>
      </a>
      <a href="#">
        <img class="mb-2 h-14 w-full rounded object-cover" src="https://avatars.githubusercontent.com/u/26369276?v=4"
          alt="Placeholder image" />
        <h4 class="mb-0.5 text-sm font-medium">Lorem ipsum dolor</h4>
        <p class="text-xs text-neutral-400">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Amet illo
          quidem eos.
        </p>
      </a>
    </div>
    <button class="ml-auto mt-4 flex items-center gap-1 text-sm text-blue-500">
      <span>View more</span>
      <ArrowRight :size="20" strokeWidth={1.5} />
    </button>
  </div>
</template>

<script lang="ts" setup>
import { ArrowRight } from 'lucide-vue-next'
</script>