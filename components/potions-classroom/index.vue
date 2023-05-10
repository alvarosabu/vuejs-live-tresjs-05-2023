<script setup lang="ts">
import { shallowRef } from 'vue'
import { TresCanvas, TresInstance } from '@tresjs/core'
import { OrbitControls } from '@tresjs/cientos'
import { BasicShadowMap, sRGBEncoding, NoToneMapping } from 'three'
import Room from './Room.vue'

const gl = {
  clearColor: '#121212',
  shadows: true,
  alpha: false,
  shadowMapType: BasicShadowMap,
  outputEncoding: sRGBEncoding,
  toneMapping: NoToneMapping,
}

const directionalLightRef = shallowRef<TresInstance>()
</script>

<template>
  <TresCanvas v-bind="gl" ref="context">
    <TresPerspectiveCamera :position="[9, 12, 9]" />
    <Suspense>
      <Room />
    </Suspense>
    <TresAmbientLight :intensity="2" />
    <TresDirectionalLight
      ref="directionalLightRef"
      :intensity="2"
      :color="'orange'"
      :position="[8, 8, 8]"
      cast-shadow
    />
    <TresDirectionalLightHelper v-if="directionalLightRef" :args="[directionalLightRef, 5]" />
    <OrbitControls />
  </TresCanvas>
</template>
