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
clicks: 5
---

# Picking NPM packages becomes more difficult

<VClicks>

* Ideally any package supports... 
* CJS (legacy)
* ESM
* running via Deno
* TS and provides own types

</VClicks>

<Code v-click="2">

```js{1|3|5|all} {at:2}
const { someFunction, someOtherVariable } = require('my-lib')

import { someFunction, someOtherVariable } from 'my-lib'

import { someFunction, someOtherVariable } from 'https://unpkg.com/my-lib/dist/index.mjs'
```

</Code>

<!--
And also: Writing and maintaining these packages!
-->

---

# Software requirements can change

---

# Software requirements ~~can~~ will change

<VClicks>

* What if you change the platform you deploy to?
  * e.g. from a docker container into lambdas or workers
* What if you decide to utilize SSR?
  * and which packages break now 👀

</VClicks>

---

# "The solution"

<VClicks>

* Use "modern" packages
* Ideally those who are universally usable
* With as little sub-dependencies as possible
* And who support all "common" formats

</VClicks>

---
layout: cover
background: https://media0.giphy.com/media/26n6WywJyh39n1pBu/giphy.gif
---
---
layout: cover
background: https://media1.giphy.com/media/l41lFw057lAJQMwg0/giphy.gif
---
---
layout: cover
background: https://media2.giphy.com/media/DMC9w6MPUXYv9Yts49/giphy.gif
---
---
layout: intro
class: filter blur-md
---

# `unjs`

<img src="https://avatars.githubusercontent.com/u/80154025" class="mx-auto mt-8 w-32"  alt="Logo of unjs">

---

# During Nuxt 2 development...

<VClicks>

* ...more and more functionalities were introduced
* At first - more or less coupled to the core
* "Nuxt-related" logic -> extracted as Nuxt module
* "General" logic -> extracted as standalone NPM package

</VClicks>

---

# Why external packages?

<VClicks>

* Decoupled from the Nuxt core
* Easier to test
* Better to maintain
* Can be reused throughout projects...
* ...even in these that are not **related to Nuxt**

</VClicks>

---

<img class="mx-auto" src="https://imgs.xkcd.com/comics/dependency.png" alt="xkcd about dependencies">

---

# `nuxt-contrib`

<img src="/nuxt-contrib.png" class="opacity-75" alt="Screenshot of the nuxt-contrib GitHub org">

---

# `nuxt-contrib`

* Contained packages used in Nuxt or Nuxt projects

<VClicks>

* From `connect` middleware over testing tools to utilities
* Evolved further to be more than just "packages from the Nuxt team"

</VClicks>

---
layout: intro
class: filter blur-md
---

# `unjs`

<img src="https://avatars.githubusercontent.com/u/80154025" class="mx-auto mt-8 w-32"  alt="Logo of unjs">

---
layout: intro
---

# `unjs`

<img src="https://upload.wikimedia.org/wikipedia/commons/6/6a/JavaScript-logo.png?20120221235433" class="mx-auto mt-8 w-32"  alt="Logo of JavaScript">

---
layout: intro
---

# `unjs`

<img src="https://avatars.githubusercontent.com/u/80154025" class="mx-auto mt-8 w-32"  alt="Logo of unjs">

---
layout: intro
---

<div class="mx-auto">
<img class="mx-auto h-100" src="/evan-you-tweet.png"  alt="Evan You tweeting: I'm excited not just about Nuxt 3 but also the amazing projects powering it under https://github.com/unjs - it's like treasure trove of great stuff.">
<a class="text-xs" href="https://twitter.com/youyuxi/status/1438171314221617153">Source</a>
</div>

---

# Let's take a look

<img v-click class="mx-auto max-w-full h-90 opacity-75" src="/unjs-website.png"/>

---
layout: intro
---

# Who has dealt with transforming URLs? ✋🏻

---
layout: intro
---

# How?

---

# 👽️ ufo - URL utils for humans

<VClicks>

* URL normalization
* Joining and resolving URLs while keeping query and hash
* Remove or add trailing/leading slash
* deduplicate slashes from URLs in general
* and way more

</VClicks>

<!--

Normalize:
* URL is properly encoded
* preserve protocol/host (if possible)

-->

---

# ufo - Show me the code!

```js {0|1-3|1-4|1-5|all}
import { joinURL } from 'ufo'

joinURL('/my/', 'nice', 'url/')
// Will yield: /my/nice/url/ 
joinURL('/a?query=yes', '/b', '/c#hash')
// ???

```

---

# ufo - Show me the code!

```js{1-6|1-7|1-8|1-9|1-10|1-11|all}
import { joinURL, resolveURL, cleanDoubleSlashes, parseURL } from 'ufo'

joinURL('/my/', 'nice', 'url/')
// Will yield: /my/nice/url/ 
joinURL('/a?query=yes', '/b', '/c#hash')
// /a?query=yes/b/c#hash - oh oh!
resolveURL('/a?query=yes', '/b#someOtherHash', '/c#hash')
// /a/b/c?query=yes#hash
cleanDoubleSlashes('https://conf.vuejs.de////schedule//')
// https://conf.vuejs.de/schedule/
parseURL('/unstorage-h3-file-server-example?file=index.js')
// { "pathname": "/unstorage-h3-file-server-example", "search": "?file=index.js", "hash": "" }
```

---
layout: intro
---

# ⚡️ H3 - Minimal h(ttp) framework

---

# H3 - Why another framework?

<VClicks class="mt-16">

* There are so many existing http frameworks for node.js already:
* connect
* express
* fastify
* koa
* hapi.js
* and more...

</VClicks>

---

# H3 - Why another framework?

<VClicks class="mt-16">

* H3 is...
* ...platform-agnostic
* ...compatible with existing stacks
* ...minimal
* ...modern
* ...extendable
* ...coming with a built-in router

</VClicks>

<!--
* ...platform-agnostic: Works perfectly in Serverless, Workers, and Node.js
* ...compatible with existing stacks: supports connect and express middleware
* ...minimal: Tiny and tree-shakable
* ...modern: Native promise support
* ...extendable: Ships with a set of composable utilities but can be extended
* ...coming with a built-in router: Super fast route matching using unjs/radix3

-->

---

# H3 - Usage

```js{0|2-4|2-6|2-7|2-8|2-10|1,4,12|all}
import { listen } from 'listhen'
import { createApp, createRouter } from 'h3'

const app = createApp()

const router = createRouter()
  .get('/', () => 'Hallo Berlin!')
  .get('/color/:color', (event) => `I like ${event.context.params.color}!`)

app.use(router)

listen(app)
```

<VClicks>

* [Check it out!](https://stackblitz.com/edit/h3-vuejs-de-conf-2022?file=package.json,index.js)

</VClicks>

<!--

* HMR h3

-->

---

# H3 - Used and mentioned by

<VClicks>

* [Nitro(pack)](https://github.com/unjs/nitro) - We will have a look at it next!
* [Nuxt 3](https://github.com/nuxt/framework) and [Nuxt Bridge](https://github.com/nuxt/bridge/) (via Nitro) <logos-nuxt-icon />
* [GestaltJS](https://github.com/gestaltjs/gestalt) - "A modern full-stack and batteries-included framework"
* [serve](https://github.com/nmathew98/serve) - "A lightweight starting point for API applications"
* [frourio-h3](https://github.com/SegaraRai/frourio-unofficial-h3) - An unofficial port of the full-stack TS framework

</VClicks>

---

# 🌍💾 unstorage - Universal Storage Layer

<VClicks>

* Powerful universal storage layer
* Unified API, < 5 kB
* Supports in-memory, filesystem, localstorage, redis and HTTP...
* ...GitHub repositories (read-only) and Cloudflare's KV-store via http and bindings
* Can be extended by creating custom drivers too!
* Also supports being used as storage server

</VClicks>

<!-- 

comparison: localforage - 28.9 kB

Using lots of storages throughout applications: Commonly FS, some DBs and LocalStorage.

-->

---

# unstorage - Example using as storage server

```js{1-2,12,14,16,18-19|3-4,7-9|3-10|3-10,15}
import { listen } from 'listhen';
import { createApp, createRouter } from 'h3';
import { createStorage } from 'unstorage';
import fsDriver from 'unstorage/drivers/fs';
import { createStorageServer } from 'unstorage/server';

const storage = createStorage({
  driver: fsDriver({ base: './' }),
});
const storageServer = createStorageServer(storage);

const app = createApp();

const router = createRouter()
  .add('/storage/*', storageServer.handle)
  .get('/', () => 'We have a file server now')

app.use(router);
listen(app);
```

[Here we go](https://stackblitz.com/edit/unstorage-file-server-vuejs-de-conf-2022?file=index.js)

---

# unstorage - Used and mentioned by

<VClicks>

* [unstorage-pinia-plugin](https://github.com/BreizhReloaded/unstorage-pinia-plugin) - A pinia plugin to persist your store via unstorage (can be any driver)
* [Fabian's Webperlen EP15](https://www.webundmobile.de/web/javascript/beliebige-speicherorte-2757448.html) - (German) article about unstorage - [repo](https://github.com/fdeitelhoff/w-m-fabians-web-perlen-ep15-unstorage)
* [file-computed](https://github.com/dishait/file-computed/) - Execute functions when the content of files change
* [Nuxt 3](https://github.com/nuxt/framework) and [Nuxt Bridge](https://github.com/nuxt/bridge/) (via Nitro) <logos-nuxt-icon />
* Also in projects [outside](https://github.com/ksmarty/advantage/tree/main) of Nuxt 3

</VClicks>

---

# ⚗️ Nitro - Build and deploy universal JavaScript servers

<VClicks>

* Toolchain and runtime framework at once
* Comes with HMR out of the box
* Supports various route rules (see Daniel's talk! 👀)
* Customizable, configurable and extendable
* Uses lots of `unjs` packages (e.g. `h3`, `unstorage` and `ufo`)

</VClicks>

---
layout: intro
---

# Deploy a JS server to **any provider**

## without changing the codebase (at most, config)

<style>
  h1 {
    @apply !text-5xl;
  }
  h2 {
    @apply !text-2xl;
  }
</style>

---

# Nitro - 👀

<div class="flex justify-center items-center h-70">

## [Let's go](https://stackblitz.com/edit/unjs-vuejs-de-conf-2022)


</div>


---

# Nitro - Used and mentioned by

<VClicks>

* [Nuxt 3](https://github.com/nuxt/framework) and [Nuxt Bridge](https://github.com/nuxt/bridge/)
  * and any project built with Nuxt 3 <logos-nuxt-icon />
* [stacks.js](https://github.com/stacksjs/stacks) - "A progressive, atomic full-stack framework"
* [vitejs/rfcs-bot](https://github.com/vitejs/rfcs-bot) - "Automation of RFCs creation for vitejs/rfcs"
* [issues-up](https://github.com/antfu/issue-up/tree/main) - "Mirror issues to the upstream repos"
* [jjw-proxy](https://github.com/jonathanjameswatson/jjw-proxy) - "Customisable Cloudflare Workers proxy"

</VClicks>

---

# And there are way more packages

<VClicks>

* We saw some during the examples already. And in addition:
* `unplugin` - Unified plugin system for all major bundlers (Vite, Rollup, Webpack, esbuild)
* `untyped` - Generate types and markdown from a config object
* `consola` - Beautiful universal console logger
* `hookable` - Async hook system
* ...and way more! Check out the [GitHub organisation](https://github.com/unjs)

</VClicks>

---

# Contributors

<VClicks>

* When you browse around the `unjs` organization, you will see these images quite often:

<div class="w-full flex justify-around my-8">
  <img class="rounded-full h-40" src="https://avatars.githubusercontent.com/u/11247099" alt="Anthony Fu">
  <img class="rounded-full h-40" src="https://avatars.githubusercontent.com/u/28706372" alt="Daniel Roe">
  <img class="rounded-full h-40" src="https://avatars.githubusercontent.com/u/5158436" alt="Pooya Parsa">
</div>

* But also lots of other individual contributors of each project!

</VClicks>

---
layout: intro
---

<div class="flex items-center justify-center h-80">

# Thanks to all of them 👏🏻👏🏻👏🏻

</div>

---

# Outro

<VClicks>

* Picking an NPM package that supports (almost) all platforms is **not easy** <sup class="text-[0.5rem]">Writing and maintaining these too</sup>
* Extracting isolated features helps maintainability and reusability throughout the ecosystem
* `unjs` packages power not only Nuxt, but also many other frameworks...
  * ...and can be used **for your app too**!

</VClicks>

<div class="flex justify-around items-center w-2/3 mx-auto mt-8" v-click>
<span class="text-3xl">Hacktoberfest 22 is on!</span>
<img v-click class="ml-16 w-48 rounded-full" src="/hacktoberfest.jpg" alt="Hacktoberfest 22 Image">
</div>


---
layout: intro
---


# Thanks a lot to my sponsors!

<img src="/sponsors.svg" class="h-70 mx-auto" alt="My GitHub sponsors">

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

* Slides: [https://lichter.link/vuejs-de-2022-slides/](https://lichter.link/vuejs-de-2022-slides/)
* Repo: [https://lichter.link/vuejs-de-2022-repo/](https://lichter.link/vuejs-de-2022-repo/)
