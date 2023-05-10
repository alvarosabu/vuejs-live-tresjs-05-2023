<script setup lang="ts">
import { TresCanvas } from '@tresjs/core'
import { BasicShadowMap, sRGBEncoding, NoToneMapping } from 'three'
import GoldSnitch from './GoldSnitch.vue'
import { OrbitControls } from '@tresjs/cientos'

const gl = {
  clearColor: '#82DBC5',
  shadows: true,
  alpha: false,
  shadowMapType: BasicShadowMap,
  outputEncoding: sRGBEncoding,
  toneMapping: NoToneMapping,
}
</script>

<template>
  <TresCanvas v-bind="gl">
    <TresPerspectiveCamera :position="[20, 20, 20]" />
    <OrbitControls />
    <Suspense>
        <GoldSnitch />
    </Suspense>
    <TresAmbientLight :intensity="1" />
  </TresCanvas>
</template>