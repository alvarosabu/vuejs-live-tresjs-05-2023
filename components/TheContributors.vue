<script setup lang="ts">
const contributors = [
  {
    name: 'Jaime Torrealba',
    avatar: 'https://avatars.githubusercontent.com/u/63722373?v=4',
    github: 'https://github.com/JaimeTorrealba',
  },
  {
    name: 'Tino Koch',
    avatar: 'https://avatars.githubusercontent.com/u/17991193?v=4',
    github: 'https://github.com/tinoooo',
  },
  {
    name: 'Wheat',
    avatar: 'https://avatars.githubusercontent.com/u/7064956?v=4',
    github: 'https://github.com/wheatjs',
  },
  {
    name: 'Konstantin',
    avatar: 'https://avatars.githubusercontent.com/u/5133074?v=4',
    github: 'https://github.com/kissu',
  },
  {
    name: 'Randysheng',
    avatar: 'https://avatars.githubusercontent.com/u/11868294?v=4',
    github: 'https://github.com/Randysheng',
  },
  {
    name: 'Madjid Taha',
    avatar: 'https://avatars.githubusercontent.com/u/1833954?v=4',
    github: 'https://github.com/madjidtaha',
  },
  {
    name: 'AlvaroSabu',
    avatar: 'https://avatars.githubusercontent.com/u/4699008?v=4',
    github: 'https://github.com/alvarosabu',
  },
  {
    name: 'You!',
    avatar: 'https://kit8.net/wp-content/uploads/edd/2022/09/Girl_avatar_preview.jpg',
    github: '',
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
