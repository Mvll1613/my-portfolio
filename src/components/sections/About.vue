<template>
  <section id="about" class="flex items-center justify-center background-white h-screen">
    <div class="flex gap-15">
      <div class="flex flex-col gap-8">
        <div>
          <h1 class="text-5xl pb-3">About Me</h1>
          <div class="border-2 rounded-xl h-0 w-150" />
        </div>

        <ul class="flex flex-col gap-8 text-2xl">
          <li
            v-for="item in ABOUT_ME_DATA"
            :key="item.label"
            class="flex"
          >
            <span class="w-40">{{ item.label }}</span>
            <span class="w-8">:</span>
            <span>{{ item.value }}</span>
          </li>
        </ul>

        <div class="mt-2">
          <h1 class="text-3xl">FIND ME ON</h1>
          <div class="flex gap-7 mt-4">
            <img
              v-for="social in SOCIAL_MEDIA_DATA"
              :key="social.alt"
              :src="social.src"
              :alt="social.alt"
              class="w-9 cursor-pointer"
              @click="handleSocMedClick(social.url)"
            >
          </div>
        </div>
      </div>

      <img
        class="w-84"
        src="/profile-pic-2.png"
        alt="Profile Picture"
      >
    </div>
  </section>
</template>

<script setup lang="ts">
  import { ABOUT_ME_DATA, SOCIAL_MEDIA_DATA } from '@/data/profile-data'

  const handleSocMedClick = (url: string) => {
    window.open(url, '_blank')
  }
</script>

