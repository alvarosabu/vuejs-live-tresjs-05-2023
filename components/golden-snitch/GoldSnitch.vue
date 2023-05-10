<script setup lang="ts">
import { ref, watchEffect } from 'vue';
import { useGLTF } from '@tresjs/cientos';

const { scene: model, nodes } = await useGLTF('/public/golden_snitch.glb', {
    draco: true,
  },
)

console.log(nodes)

const modelRef = ref(null)

watchEffect(() => {
    if (modelRef.value) {
        console.log(modelRef.value)
        modelRef.value.scale.set(0.1, 0.1, 0.1)
        modelRef.value.updateMatrixWorld()
    }
})

</script>

<template>
   <primitive ref="modelRef" :object="nodes.Sketchfab_model"> </primitive>
</template>