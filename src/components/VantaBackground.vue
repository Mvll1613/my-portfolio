<template>
  <div ref="vantaRef" class="vanta-bg">
    <slot />
  </div>
</template>

<script setup lang="ts">
  import { ref, onMounted } from "vue"
  import * as THREE from "three"
  import NET from "vanta/dist/vanta.net.min"

  const vantaRef = ref<HTMLElement | null>(null)

  onMounted(() => {
    if (!vantaRef.value) return

    NET.default({
      el: vantaRef.value,
      THREE,

      mouseControls: true,
      touchControls: true,
      gyroControls: false,
      minHeight: 200,
      minWidth: 200,
      scale: 1.00,
      scaleMobile: 1.00,
      color: 0x00a8e8,
      backgroundColor: 0x00171f,
      maxDistance: 15.00,
      points: 13,
      spacing: 15
    })
  })
</script>

<style>
  .vanta-bg {
    width: 100%;
    height: 100%;
  }
</style>
