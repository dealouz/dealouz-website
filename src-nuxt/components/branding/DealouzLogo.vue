<template>
  <div class="flex items-center gap-2">
    <img
      src="../../assets/images/logo-dealouz-256x256.png"
      alt="Logo Dealouz"
      :height="props.size"
      :width="props.size"
    />
    <span
      v-if="props.large"
      class="relative top-1 font-bold text-light-500"
      :class="{
        'text-2xl': Number(props.size) >= 40,
        'text-lg': Number(props.size) < 40,
      }"
    >
      Dealouz
    </span>
  </div>
</template>

<script lang="ts" setup>
/**
 * Type definitions for the DealouzLogo component props
 */
type DealouzLogoProps = {
  size: number | string
  large: boolean
}

/**
 * Define the DealouzLogo props.
 */
const props: DealouzLogoProps = defineProps({
  size: {
    type: [Number, String],
    default: 40,
  },
  large: {
    type: Boolean,
    default: false,
  },
})
</script>
