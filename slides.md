---
theme: ./theme
title: '`unjs` - Unified JavaScript solutions'
website: lichter.io
handle: TheAlexLichter
favicon: https://lichter.io/img/me@2x.jpg
highlighter: shiki
lineNumbers: true
layout: intro
---

# `unjs`

## <span class="text-[#f0db4f]">Unified</span> JavaScript solutions 

### vuejs.de Conf 2022

<style>
  h1 {
    @apply !text-5xl;
  }

  h2 {
    @apply !text-2xl !my-16;
  }

  h3 {
    @apply !text-xl
  }
</style>  

---
layout: two-cols
heading: About me
---

<template v-slot:default>
<div class="flex flex-col justify-center items-center h-full">
<img
  class="w-75 rounded-full"
  src="https://lichter.io/img/me@2x.webp"
  />
  <h2 class="mt-4">Alexander Lichter</h2>
</div>
</template>

<template v-slot:right>
<VClicks class="space-y-2 mt-10 text-xl h-full">

* <mdi-account-check class="text-green-100" /> **Web Development Consultant**
* <mdi-microphone /> Speaker & Instructor
* <logos-nuxt-icon /> Nuxt.js Maintainer
* <mdi-twitter class="text-blue-400" /> @TheAlexLichter
* <mdi-web /> [https://lichter.io](https://lichter.io)
* <mdi-github /> [manniL](https://github.com/manniL)

</VClicks>
</template>

---
layout: intro
---

# JavaScript runs *everywhere*

---

# JavaScript runs *everywhere*

<br><br>

<div class="flex flex mt-8 justify-around">
<VClicks>

<img src="/firefox.png" class="w-24" alt="Firefox Developer Edition Logo">
<img src="https://nodejs.org/static/images/logo.svg" class="w-32" alt="Firefox Developer Edition Logo">

<img src="https://deno.land/logo.svg?__frsh_c=2y6shjpc605g" class="w-24" alt="Deno Logo">

<img src="/cf-workers.svg" class="w-64 text-white fill-current" alt="Cloudflare Workers Logo">

</VClicks>
</div>

---


# Nuxt 2 and Nuxt 3 -> external packages
# Why? (Easier to test, can be reused)

---

# Let's take a look

<img v-click class="mx-auto max-w-full h-90" src="/unjs-website.png"/>

---

# 👽️ ufo - URL utils for humans


---

# 🧵 scule - String case utils ?

* PascalCase
* camelCase
* kebab-case
* snake-case
* Upperfirst
* lowerfirst
* splitByCase 

---

# Defu


---

# ohmyfetch

* Universal wrapper around `fetch`
* Usable with Node (polyfill, native, or undici)
* As well as in the browser and in workers!

---

# 🌍💾 unstorage - Universal Storage Layer

* Powerful universal storage layer
* Unified API, < 5 kB
* Supports in-memory, filesystem, localstorage, redis and HTTP
* As well as GitHub repositories (read-only) and Cloudflare's KV-store via http and bindings
* Can be extended by creating custom drivers too!
* And be used as storage server too with ease

Notes:
* https://github.com/dishait/file-computed/ ?
* Combine stores if wanted
* 

<!-- 

localforage: 28.9 kB

Typically, we choose one or more data storages based on our use-cases like a filesystem, a database like Redis, Mongo, or LocalStorage for browsers but it will soon start to be lots of trouble for supporting and combining more than one or switching between them. For javascript library authors, this usually means they have to decide how many platforms they support and implement storage for each.

💡 Unstorage solution is a unified and powerful Key-Value (KV) interface that allows combining drivers that are either built-in or can be implemented via a super simple interface and adding conventional features like mounting, watching, and working with metadata.

-->

---

# H3 - Minimal h(ttp) framework

* Portable: Works perfectly in Serverless, Workers, and Node.js
* Compatible: Support connect/express middleware
* Minimal: Small, tree-shakable and zero-dependency
* Modern: Native promise support
* Extendable: Ships with a set of composable utilities but can be extended
* Router: Super fast route matching using unjs/radix3
---

# Nitro

* 

---

# Outro

* 
* 

---

---
layout: two-cols
heading: Thank you for your attention!
---

<template v-slot:default>
<div class="flex flex-col justify-center items-center h-full">
<img
  class="w-75 rounded-full"
  src="https://lichter.io/img/me@2x.webp"
  />
  <h2 class="mt-4">Alexander Lichter</h2>
</div>
</template>

<template v-slot:right>

* <mdi-account-check class="text-green-100" /> **Web Development Consultant**
* <mdi-microphone /> Speaker & Instructor
* <logos-nuxt-icon /> Nuxt.js Maintainer
* <mdi-twitter class="text-blue-400" /> @TheAlexLichter
* <mdi-web /> [https://lichter.io](https://lichter.io)
* <mdi-github /> [manniL](https://github.com/manniL)

</template>

<style>
  ul {
    @apply space-y-2 mt-10 text-xl h-full;
  }
</style>

---
layout: intro
---

# Slides / Repo

## TODO
