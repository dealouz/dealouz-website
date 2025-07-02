<template>
  <div
    class="relative flex w-full items-center justify-between gap-4 rounded-xl border border-orange-200 bg-[#FFF8F0] px-6 py-8"
  >
    <!-- Top   -->
    <div class="items-center justify-between">
      <!-- Left part: Promo info -->
      <div class="flex items-center gap-4">
        <p class="text-3xl font-bold text-orange-600">{{ discount }}</p>
        <p class="text-brown-800 text-base">{{ description }}</p>
      </div>

      <!-- Right part: Promo code -->
      <div
        class="relative ml-4 flex flex-col items-center justify-center rounded-md bg-orange-400 px-4 py-3 text-white shadow-sm"
      >
        <span class="text-sm font-medium uppercase tracking-widest">Code</span>
        <span class="text-lg font-bold">{{ promoCode }}</span>
        <div class="absolute -right-2 -top-2 h-5 w-5 rotate-45 rounded-sm bg-white/40"></div>
      </div>
    </div>

    <!-- Bottom   -->
    <div>
      <p v-if="expirationDate" class="text-brown-500 text-sm">Valable jusqu’au {{ expirationDate }}</p>
    </div>
  </div>
</template>

<script lang="ts" setup>
/**
 * Type definitions for the DealouzPromoCodeCard component props
 */
export type DealouzPromoCodeCardProps = {
  promoCode: string
  discount: string
  description: string
  expirationDate?: string
}

const props: DealouzPromoCodeCardProps = defineProps({
  promoCode: {
    type: String,
    required: true,
  },
  discount: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    required: true,
  },
  expirationDate: {
    type: String,
    default: null,
  },
})
</script>
