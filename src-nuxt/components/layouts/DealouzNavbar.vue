<template>
  <div class="flex h-[80px] w-full flex-wrap items-center justify-around bg-gray-700 px-4 py-1.5">
    <DealouzLogo :large="true" :size="55" />
    <FlapiSearchBar placeholder="Rechercher un marchand..." title="Search" />
  </div>
</template>
<script setup lang="ts">
import DealouzLogo from '~/components/branding/DealouzLogo.vue'
</script>
