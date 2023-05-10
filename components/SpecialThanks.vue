<script setup lang="ts">
const contributors = [
  {
    name: 'Cody Bennet',
    avatar: 'https://avatars.githubusercontent.com/u/23324155?v=4',
    github: 'https://github.com/CodyJasonBennett',
  },
  {
    name: 'Verekia',
    avatar: 'https://avatars.githubusercontent.com/u/522007?v=4',
    github: 'https://github.com/verekia',
  },
  {
    name: 'Patak',
    avatar: 'https://avatars.githubusercontent.com/u/583075?v=4',
    github: 'https://github.com/patak-dev',
  },
  {
    name: 'Yaël Guilloux',
    avatar: 'https://avatars.githubusercontent.com/u/1385263?v=4',
    github: 'https://github.com/Tahul',
  },
  {
    name: 'Daniel Roe',
    avatar: 'https://avatars.githubusercontent.com/u/28706372?v=4',
    github: 'https://github.com/danielroe',
  },
  {
    name: '@0xca0a',
    avatar: 'https://avatars.githubusercontent.com/u/2223602?v=4',
    github: 'https://github.com/drcmda',
  },
]
</script>
<template>
  <div class="pt-8 grid grid-cols-4 gap-8">
    <div class="flex flex-col items-center" v-for="{ avatar, name } of contributors">
      <img :src="avatar" class="rounded-full w-20 h-20 mb-2 object-cover border border-gray-200" />
      <h2 class="important-text-sm">{{ name }}</h2>
    </div>
  </div>
</template>
