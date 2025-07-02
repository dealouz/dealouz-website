<template>
  <div class="my-8 flex items-center justify-center">
    <section class="grid w-full max-w-3xl gap-4">
      <DealouzPromoCodeCard
        v-for="(promoCode, index) in promoCodes"
        :key="index"
        :promoCode="promoCode.promoCode"
        :discount="promoCode.discount"
        :description="promoCode.description"
        :expirationDate="promoCode.expirationDate"
        @apply="(code) => console.log(`Applying promo code: ${code}`)"
      />
    </section>
  </div>
</template>

<script lang="ts" setup>
import type { DealouzPromoCodeCardProps } from '@/components/cards/DealouzPromoCodeCard.vue'
import { DateTime } from 'luxon'
import DealouzPromoCodeCard from '~/components/cards/DealouzPromoCodeCard.vue'

const promoCodes: DealouzPromoCodeCardProps[] = [
  {
    promoCode: 'DEALOUZ10',
    discount: '5%',
    description: 'Code promo Darty : 10% offerts sur le gros électroménagers',
    expirationDate: DateTime.fromObject({ year: 2025, month: 6, day: 30 }).toISODate() || undefined,
  },
  {
    promoCode: 'DEALOUZ20',
    discount: '10%',
    description: 'Code promo Darty : 10% offerts sur le petit électroménagers',
    expirationDate: DateTime.fromObject({ year: 2025, month: 6, day: 30 }).toISODate() || undefined,
  },
  {
    promoCode: 'DEALOUZ30',
    discount: '15%',
    description: 'Code promo Darty : 15% offerts sur les téléviseurs',
    expirationDate: DateTime.fromObject({ year: 2025, month: 6, day: 30 }).toISODate() || undefined,
  },
  {
    promoCode: 'DPFJIV',
    discount: '10€',
    description: 'Code promo Darty : 10€ offerts sur les produits de la catégorie "Informatique"',
  },
  {
    promoCode: 'DARTY20',
    discount: '20%',
    description: 'Code promo Darty : 20% offerts sur les produits de la catégorie "Son"',
    expirationDate: DateTime.fromObject({ year: 2025, month: 6, day: 30 }).toISODate() || undefined,
  },
  {
    promoCode: 'DARTY30',
    discount: '30%',
    description: 'Code promo Darty : 30% offerts sur les produits de la catégorie "Photo"',
    expirationDate: DateTime.fromObject({ year: 2025, month: 6, day: 30 }).toISODate() || undefined,
  },
]
</script>
