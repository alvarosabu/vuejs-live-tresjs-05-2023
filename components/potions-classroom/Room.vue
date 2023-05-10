<script setup lang="ts">
import { useGLTF } from '@tresjs/cientos'
import { shallowRef, watchEffect } from 'vue'

const { scene: classroom, nodes } = await useGLTF('/potions-classroom.glb')

classroom.traverse(child => {
  if (child.isMesh) {
    child.castShadow = true
    child.receiveShadow = true
  }
})
</script>
<template>
  <primitive ref="featherRef" :object="classroom" />
</template>
