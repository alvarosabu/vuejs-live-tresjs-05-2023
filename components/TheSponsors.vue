<script setup lang="ts">
const contributors = [
  {
    name: 'Danny-Devs',
    avatar: 'https://avatars.githubusercontent.com/u/38071276?v=4',
    github: 'https://github.com/Danny-Devs',
  },
  {
    name: 'Marc Backes',
    avatar: 'https://avatars.githubusercontent.com/u/1444915?v=4',
    github: 'https://github.com/themarcba',
  },
  {
    name: 'easingthemes',
    avatar: 'https://avatars.githubusercontent.com/u/2750284?v=4',
    github: 'https://github.com/easingthemes',
  },
  {
    name: 'kissu',
    avatar: 'https://avatars.githubusercontent.com/u/5133074?v=4',
    github: 'https://github.com/kissu',
  },
  {
    name: 'masedri',
    avatar: 'https://avatars.githubusercontent.com/u/21109779?v=4',
    github: 'https://github.com/masedri',
  },
  {
    name: 'Storyblok',
    avatar: 'https://avatars.githubusercontent.com/u/13880908?s=200&v=4',
    github: 'https://github.com/storyblok',
  },
]
</script>
<template>
  <div class="pt-8 grid grid-cols-4 gap-8">
    <div class="flex flex-col items-center" v-for="{ avatar, name } of contributors">
      <img :src="avatar" class="rounded-full w-20 h-20 mb-2 object-cover border border-gray-200" />
      <h2 class="important-text-sm">{{ name }}</h2>
    </div>
    <div class="flex items-center mb-3">
      <img
        src="https://avatars.githubusercontent.com/u/4699008?v=4"
        class="rounded-full w-10 h-10 mr-4 object-cover border border-gray-200"
      />
      <iframe
        src="https://github.com/sponsors/alvarosabu/button"
        title="Sponsor alvarosabu"
        height="35"
        width="116"
        style="border: 0"
      ></iframe>
    </div>
  </div>
</template>
