---
# try also 'default' to start simple
theme: penguin
colorSchema: 'dark'
preload: false
# https://sli.dev/custom/highlighters.html
highlighter: shiki
themeConfig:
  logoHeader: https://res.cloudinary.com/alvarosaburido/image/upload/v1666359605/as-portfolio/Pixel_Avatar_lhbjva.png
  eventLogo: 'https://do3z7e6uuakno.cloudfront.net/uploads/event/logo/1120448/644d4dd0a72cb0b44eec66adbc5bd9d3.png'
  eventUrl: 'https://vuejs.amsterdam/'
  twitter: '@alvarosabu'
  twitterUrl: 'https://twitter.com/alvarosabu'
css: unocss
---

<!-- <EmbedExperiment width="860" height="450"  src="https://playground.tresjs.org/experiments/portal-journey"  /> -->
<!-- <PotionsClassroom width="860" height="450"  /> -->

---
layout: intro
---

# ~~TresJS ▲ ■ ●~~

## ~~A declarative way of doing 3D with Vue components~~

---
layout: intro
---

# TresJS & the Chamber of Vue

## Unlocking the Mysteries of 3D Rendering

<img src="/golden-snitch.gif" class="absolute w-40 top-8 right-50%"/>

<!-- TODO: Add 3D version of Snitch -->
---
layout: presenter
twitter: '@alvarosabu'
twitterUrl: https://twitter.com/alvarosabu
presenterImage: /avatar.jpeg
---

# Alvaro Saburido

DevRel Engineer at <a href="https://www.storyblok.com/"><logos-storyblok-icon /> Storyblok</a>

- Barcelona, Spain 🇻🇪 🇪🇸
- Creating content on <a href="https://www.youtube.com/channel/AlvaroDevLabs" ><logos-youtube-icon mr-1 />AlvaroDevLabs</a>
- Blog & Portfolio <a href="https://alvarosaburido.dev">alvarosaburido.dev</a>
- Say hi at <a href="https://twitter.com/alvarosabu"><logos-twitter mr-1 />@alvarosabu</a>
- <a href="https://elk.zone/mas.to/@alvarosabu">@alvarosabu@mas.to</a>

<!-- TODO: Add Midjourney Version of the avatar as a Wizard -->

---
layout: text-image
media: /kid.jpeg
---

# The boy who lived

<v-click>

Playing video games.

</v-click>
---
layout: two-cols
---
# Still a kid

::right::

![bigkid](/bigkid.jpg)
<!-- Show picture now playing -->

<!-- That kid honestly never left and still is a part of me nowadays -->

---
layout: two-cols
---

# Motivation

![](/crashbandicoot.jpeg)

::right::

![](/harry-potter-ps1.webp)

---
layout: text-image
media: /threejs-journey.png
---

# ThreeJS to the rescue <logos-threejs class="fill-white" />

It's a JavaScript library that leverages WebGL to render 3D scenes in the browser. 


> Makes it easier to work with 3D on the browser 

Check [ThreeJS docs](https://threejs.org/) and [ThreeJS Journey](https://threejs-journey.com/)

---
layout: text-image
media: https://docs.pmnd.rs/_next/static/media/react-three-fiber.f038c399.jpg

---

# React-three-fiber

React-three-fiber is a **custom React renderer for three.js**. Made by **pmndrs**, is a very popular library for React developers.

```jsx
createRoot(document.getElementById('root')).render(
  <Canvas>
    <ambientLight />
    <pointLight position={[10, 10, 10]} />
    <Box position={[-1.2, 0, 0]} />
    <Box position={[1.2, 0, 0]} />
  </Canvas>,
)
```

Check it [here](https://github.com/pmndrs/react-three-fiber)

---

![](https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExNzY5MmZjYzE2NjUxYzY1NjRmYTljY2M4ZmYxMGMxNjk5NjJiMzNjNSZlcD12MV9pbnRlcm5hbF9naWZzX2dpZklkJmN0PWc/8VLgtJqaxIlhu/giphy.gif)

---
layout: two-cols
---

# TroisJS & Lunchbox


![](/troisjs.png)
[Link](https://troisjs.github.io/)

::right::

![](/lunchbox.png)
[Link](https://lunchboxjs.com/)

---
layout: two-cols
preload: false
---

# TresJS

Is a Vue custom renderer that allows you to build 3D scenes **declaratively** by using ThreeJS as Vue components.

Tres (Spanish 🇪🇸 word for "three", pronounced `/tres/` ) in reference to the **ThreeJS library**. I'm latin and the french word was already used for another library 🥸.

::right::

<LoveVueThreeJS />

---

# Why TresJS?

<v-clicks>

- Up to date with latest ThreeJS with 0-to-none maintenance 😃
- Lightweight 🪶
- Verbose and easy to use 🤓
- DX focused 🧑‍💻
- TypeScript support 🤖
- Performant even with reactivity ⚡️ powered by <a href="https://vitejs.dev/"><i class="icon-logos-vitejs" /> ViteJS </a>
- 3D Ecosystem for Vue community 🌳 🤝

</v-clicks>

---
layout: two-cols
preload: false
---

# Getting started

```bash
pnpm add @tresjs/core three -D
```

or play with it on [Stackblitz](https://stackblitz.com/edit/tresjs-basic?file=README.md)


::right::

<EmbedExperiment width="400" height="450" src="https://playground.tresjs.org/experiments/tres-basic" />

---
layout: two-cols
---

# Setting up the Canvas

Before we can create an Scene, we need a DOM element to render it to.

With **TresJS** you only need to add the default component `<TresCanvas />` to the template of your Vue component.

::right::

```html
<script setup>
import { TresCanvas } from '@tresjs/core'
</script>

<template>
  <TresCanvas> 
    // Your scene is going to live here
  </TresCanvas>
</template>
```

<Warning>
It's important that all components related to the scene live between the <b>TresCanvas</b> component. 

</Warning>

---
layout: two-cols
---

# Setting up the Scene

![](/scene-diagram.png)


::right::

Every 3D experience needs at least the following components:

<v-clicks>

- Objects
- A **Camera** to see the objects
- An **Scene** to put all together
- A **Renderer** to render it to the canvas (DOM)

</v-clicks>

---
layout: two-cols
---

# Setting up the Scene

So if you were using plain ThreeJS you would need to do something like this:

```ts {1|2|4-6|8}
const scene = new THREE.Scene()
const camera = new THREE.PerspectiveCamera()

const renderer = new THREE.WebGLRenderer({
  canvas: _canvas,
})

renderer.render(scene, camera)
```

::right::

<v-click>

# Da TresJS way 🤓

```html {2,5|3|4}
<template>
  <TresCanvas>
    <TresPerspectiveCamera />
    <!-- All your objects will live here-->
  </TresCanvas>
</template>
```

</v-click>

---
layout: two-cols
---

# Adding an Object

If we where using plain ThreeJS:

```ts {1,2|4,5|7|8}
const geometry = 
  new THREE.TorusGeometry(1, 0.5, 16, 32)

const material = 
  new THREE.MeshBasicMaterial({ color: 'orange' })

const donut = new THREE.Mesh(geometry, material)
scene.add(donut)
```

::right::

<v-click>

# Da TresJS way 🤓

```html {3,6|4|5|all}
<TresCanvas>
  <TresPerspectiveCamera />
    <TresMesh >
      <TresTorusGeometry :args="[1, 0.5, 16, 32]" />
      <TresMeshBasicMaterial color="orange" />
    <TresMesh />
</TresCanvas>
```
</v-click>

---
preload: false
---

<EmbedExperiment width="860" height="450"  src="https://playground.tresjs.org/experiments/tres-donut"  />

---

![](https://media.giphy.com/media/jcrz9fl2rfico/giphy.gif)

---

# From ThreeJS Instances to Components

<div class="grid grid-cols-3 gap-4 w-full">
  <img src="/three-latest.png"/>
  <div class="flex flex-col items-center">
   <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOGI1ODE1NTk2ZWYxMTU2YzI3ZGQzZDlmOWZiMzc1MTRkNzVmMDhhMiZlcD12MV9pbnRlcm5hbF9naWZzX2dpZklkJmN0PWc/LMJY0aqW2QHhTPEJJj/giphy.gif" v-click />
   <p v-click>a.k.a Custom Renderer</p>
  </div>
  <img src="/vue-components.png" v-click />
</div>


--- 
layout: two-cols
---

# Arguments

```html
<TresPerspectiveCamera 
  :args="[45, width/ height, 1, 1000]"
/>
```

::right::

<br />
<br />



<v-click>
```ts
const camera = 
  new PerspectiveCamera(45, width/ height, 1, 1000)

scene.add(camera)
```
</v-click>

---
layout: two-cols
---

# Props

```html
<TresPerspectiveCamera 
  :fov="45"
  :aspect="width/ height"
  :near="1"
  :far="1000"
/>
```

::right::

<br />
<br />



<v-click>
```ts
const camera = 
  new PerspectiveCamera()

camera.fov = 45
camera.aspect = width/ height
camera.near = 1
camera.far = 1000

scene.add(camera)
```
</v-click>

---
layout: two-cols
---

# Slots

```html
<TresMesh >
  <TresTorusGeometry :args="[1, 0.5, 16, 32]" />
  <TresMeshBasicMaterial color="orange" />
</TresMesh>
```

::right::

<br />
<br />


<v-click>
```ts
const geometry = 
  new TorusGeometry(1, 0.5, 16, 32)

const material = 
  new MeshBasicMaterial({ color: 'orange' })

const donut = new Mesh(geometry, material)
// same as donut.geometry = geometry and
// donut.material = material
scene.add(donut)
```

</v-click>

---

# Revelio Demonstrum 🧙🏼‍♂️

![](https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExYTNkODY1M2RjMWYyYTNhMzcxZWNlZTNiNGNiMDEzMzkzZTFlMmIzYSZlcD12MV9pbnRlcm5hbF9naWZzX2dpZklkJmN0PWc/4Pcf0yfcGUNgY/giphy.gif)

---
layout: text-image
media: /cientos.png
---

# Cientos package

Cientos (Spanish word for "hundreds", pronounced `/θjentos/` ) is a collection of useful ready-to-go abstractions and components that are not part of the core package

```bash
pnpm add @tresjs/cientos -D
```

--- 

# You got it? Tres-cientos --> Three hundred

<v-click>

![](https://media.giphy.com/media/UWERvU4Nzn1ExkPKTx/giphy.gif)

</v-click>

---
layout: two-cols
---

# Cientos package

![cientos](/cientos.png)

::right::

```
@trejs/cientos/
├── Abstractions/
│   ├── Text3D
│   └── useAnimations
├── Controls/
│   ├── OrbitControls
│   └── TransformControls
├── Loaders/
│   ├── useGLTF
│   ├── GLTFModel
│   ├── useFBX
│   └── FBXModel
├── Shapes/
│   └── Plane
└── Misc/
    └── useTweakPane
```

---
layout: two-cols
preload: false
---

# Levioso (Float)

The `cientos` package provides a `<Levioso />` wrapper that makes it content... float, just like Magic 🪄✨

::right::

<LeviosoDemo style="width:400px; height: 200px; min-height: 200px; margin: 2rem 0; border-radius: 8px; overflow:hidden;"/>


![Leviosa](https://media.giphy.com/media/HaCFT5ghY6L1m/giphy.gif)


---

# TresJS EcoSystem 🌳

<div class="w-2/3">

![](/tresjs-ecosystem.png)

</div>

___

# Roadmap

![]()

---
layout: text-image
media: /playground.png
---
# Resources

- [TresJS Documentation](https://tresjs.org)
- [Cientos Documentation](https://cientos.tresjs.org)
- [TresJS Playground](https://playground.tresjs.org/)
- [StackBlitz Collection](https://stackblitz.com/@alvarosabu/collections/tresjs)
- [Discord](https://discord.gg/y8DRxvyE) 
- TresJS Tutorials [YouTube Channel](https://www.youtube.com/watch?v=ZM7EeS75sYM&list=PLi-X1Ojrrmi_V15dXJf_XKdss0dlDzSwa)

--- 

## Contributors

<TheContributors />

---



### Contributing

[Time has come](https://github.com/Tresjs/tres/settings)

![](https://media.giphy.com/media/3UtEIg06e3uz6/giphy.gif)

---

### Thanks to my sponsors

<TheSponsors />

---

### Special Thanks

<SpecialThanks />



---
layout: new-section
---

# Thank you 🙏

![](https://media.giphy.com/media/28HuTvEHje7v1ngGAm/giphy.gif)
---