<template>
  <div>
    <div class="flex gap-4">
      <div>
        <h3 class="mb-2 text-sm font-medium">Startup</h3>
        <a href="#" class="mb-1 block text-sm text-neutral-400">Bookkeeping</a>
        <a href="#" class="block text-sm text-neutral-400">Invoicing</a>
      </div>
      <div>
        <h3 class="mb-2 text-sm font-medium">Scaleup</h3>
        <a href="#" class="mb-1 block text-sm text-neutral-400">Live Coaching</a>
        <a href="#" class="mb-1 block text-sm text-neutral-400">Reviews</a>
        <a href="#" class="block text-sm text-neutral-400">Tax/VAT</a>
      </div>
      <div>
        <h3 class="mb-2 text-sm font-medium">Enterprise</h3>
        <a href="#" class="mb-1 block text-sm text-neutral-400">White glove</a>
        <a href="#" class="mb-1 block text-sm text-neutral-400">SOX Compliance</a>
        <a href="#" class="block text-sm text-neutral-400">Staffing</a>
        <a href="#" class="block text-sm text-neutral-400">More</a>
      </div>
    </div>
    <button class="ml-auto mt-4 flex items-center gap-1 text-sm text-blue-500">
      <span>View more</span>
      <ArrowRight :size="20" stroke-width="1.5" />
    </button>
  </div>
</template>

<script lang="ts" setup>
import { ArrowRight } from 'lucide-vue-next'
</script>