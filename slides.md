---
# You can also start simply with 'default'
theme: default
background: https://cover.sli.dev
---
---
transition: slide-up
layout: image
image: /assets/backgrounds/fun_with_flags.jpg
---
<!-- FIRST SLIDE -->
<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl text-red slidev-icon-btn opacity-50 !border-none !hover:text-red-500">
    <carbon-logo-github />
  </a>
</div>
---
layout: section
---
Where are we coming from?
---
layout: section
class: text-center
title: Feature Flags
---
# 🚩 FEATURE FLAGS 🚩
<q > A short tour... </q>
---
layout: quote
level: 2
transition: slide-left
class: text-center
---

<div class="font-oblique">
  <q class="text-2xl"><span v-mark.highlight.yellow="1">Feature flags</span> are a software development technique to <span v-mark.highlight.yellow="2">turn specific features</span> or functionality <span v-mark.highlight.yellow="3">on or off</span> without changing the code. They act like switches that control access to certain parts of an application.</q>
</div>

<!--
The quint essence of this quote is: Feature Flags * turn specific features * on or off
-->
---
level: 2
layout: header-text
---

::header::
# This spans both

::text::
<ul>
  <li v-click class="font-size-6"> 🚫  Permissions </li>
  <li v-click class="font-size-6"> ⏳  Early Access </li>
  <li v-click class="font-size-6"> ✅  Opt In </li>
  <li v-click class="font-size-6"> 🍰  Incremental Rollout </li>
  <li v-click class="font-size-6"> 🛑  Block Users </li>
  <li v-click class="font-size-6"> 😵  Kill Switch </li>
  <li v-click class="font-size-6"> 💪🏻 Power Users </li>
  <li v-click class="font-size-6"> 🛠️ Maintenance </li>
  <li v-click class="font-size-6"> 🌅  Sunset </li>
</ul>

<style scoped>
ul {
  list-style-type: none;
  li {
    margin: 0;
  }
}
</style>

<!--
Permission:
Early Access
Opt-In: Zu etwas aktiv entscheiden
Incremental Rollout
Block Users
Kill Switch
Power Users
Maintenance
Sunset
-->
---
layout: quote
---
# What is our Solution?
---
layout: quote
class: text-center
---
<div>
  <img class="h-80 mx-auto" src="/assets/backgrounds/fliptsoftware-flipt.svg"/>
  <h1 class="font-bold">Flipt</h1>
</div>

<img
  v-click
  v-motion
  :initial="{ x: -200, y: 80, rotate: 30 }"
  :enter="{ x: -100, y: -25 }"
  :leave="{ x: -200, y: 80 }"
  class="w-50"
  src="./assets/backgrounds/gopher.svg"
/>

---
transition: slide-up
layout: section
class: text-center
---
<img class="mx-auto" src="./assets/backgrounds/openfeature.svg" />
<img v-click class="mx-auto w-40" src="./assets/backgrounds/cloudnative.svg" />

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub" title="Open in GitHub"
    class="opacity-50 !border-none !hover:text-red-500 my-auto">
    <img class="mx-auto w-20" src="./assets/backgrounds/openfeature.svg" />
  </a>
</div>

<style>
a {
  align-content: center;
}
</style>
---
layout: header-text
transition: slider-up
---
::header::
<h1 class="font-size-12 font-bold">What are the benefits?</h1>

::text::
<ul class="font-size-10">
  <li v-click>❗️Standard</li>
  <li v-click>📦 Packages for every Language</li>
  <li v-click>🔄 Easy swappable provider</li>
  <li v-click>🤝 A big Community</li>
</ul>

<style scoped>
ul {
  list-style-type: none;
  li {
    margin: 0;
  }
}
</style>
---
layout: image
image: /assets/backgrounds/flipt-dashboard.png
class: background-postion-top
backgroundPosition: top
---
<arrow v-click="1" x1="350" y1="100" x2="175" y2="80" color="red" width="2" arrowSize="0.25" />
<arrow v-click="2" x1="250" y1="140" x2="75" y2="120" color="red" width="2" arrowSize="0.25" />
<arrow v-click="3" x1="250" y1="160" x2="100" y2="155" color="red" width="2" arrowSize="0.25" />
<style>
.background-postion-top {
  background-position: top !important;
}
</style>
---
layout: header-text
transition: slider-up
---
::header::
<h1 class="font-size-12 font-bold"> Feature-Flags? Variants? Segments?</h1>
::text::
<ul class="font-size-6">
    <li>Feature-Flags
        <ul v-click>
            <li v-click="4">Turn functionality / features - on / off</li>
        </ul>
    </li>
    <li>Segments
      <ul v-click>
          <li v-click="5">Its kinda a rule </li>
          <li v-click="6">Ex. Users who haven't finished the onboarding</li>
      </ul>
    </li>
    <li>Variants
        <ul v-click>
            <li v-click="7">Need a Segment!</li>
            <li v-click="8">Ex. Disable different sides of the application</li>
            <li v-click="9">Ex. Show other colors</li>
        </ul>
    </li>
</ul>
---
layout: section
class: text-center font-bold
---
# Lets 🧑‍💻
---
layout: header-text
class: mx-auto
---
::header::
<h1 class="font-size-12"> Lets 🧑‍💻 </h1>
::text::
````md magic-move {lines: true}
```ts {*|1|3|5|6,8,10|7,9|*}
OpenFeature.setProvider(New Provider());

const featureFlags = OpenFeature.getClient();

const withCows = await featureFlags.getBooleanValue("with-cows", false);
if(withCows) {
  res.send(cowsay.say( { text: "Hello World!" });
} else {
  res.send("Hello World!");
}
```

```ts {*|1-2}
import { OpenFeature } from '@openfeature/web-sdk';
import { FliptWebProvider } from '@openfeature/flipt-web-provider';

OpenFeature.setProvider(New Provider());

const featureFlags = OpenFeature.getClient();

const withCows = await featureFlags.getBooleanValue("with-cows", false);
if(withCows) {
  res.send(cowsay.say( { text: "Hello World!" });
} else {
  res.send("Hello World!");
}
```

```ts{4-6|8|all}
import { OpenFeature } from '@openfeature/web-sdk';
import { FliptWebProvider } from '@openfeature/flipt-web-provider';

const provider = new FliptWebProvider(FLIPT_API_NAMESPACE, {
  url: FLIPT_API_URL
});

OpenFeature.setProvider(provider);

const featureFlags = OpenFeature.getClient();

const withCows = await featureFlags.getBooleanValue("with-cows", false);
if(withCows) {
  res.send(cowsay.say( { text: "Hello World!" });
} else {
  res.send("Hello World!");
}
```
````
---
transition: slide-left
layout: section
class: text-center font-bold
---
# Rules 👨‍⚖️
---
transition: slide-up
layout: header-text
---
::header::
<h1 class="font-size-12 font-bold">Clear Naming</h1>
<h3>Give your keys a unique and clear name</h3>
::text::

<div>
  <ul>
    <li v-click>
      <span class="font-bold color-green-700 font-size-8">DO:</span>
      <ul>
        <li>
          <span class="font-size-6"> allow_user delete | allow_user_edit</span>
        </li>
      </ul>
    </li>
    <br />
    <br />
    <br />
    <li v-click>
      <span class="font-bold color-red-700 font-size-8">DO NOT:</span>
      <ul>
        <li>
          <span class="font-size-6">user_control</span>
        </li>
      </ul>
    </li>
  </ul>
</div>

<style scoped>
ul {
  list-style-type: none;
  li {
    margin: 0;
  }
}
</style>
---
transition: slide-up
layout: header-text
---
::header::
<h1 class="font-size-12 font-bold">Fail Safe</h1>
<h3 v-click>Positively enable Features</h3>
::text::

<div>
  <ul>
    <li v-click>
      <span class="font-bold color-green-700 font-size-8">DO:</span>
      <ul>
        <li>
          <span class="font-size-6">enable-maintenance-mode</span>
        </li>
        <li>
          <span class="font-size-6">enable-maintenance-announcement</span>
        </li>
      </ul>
    </li>
    <br />
    <br />
    <br />
    <li v-click>
      <span class="font-bold color-red-700 font-size-8">DO NOT:</span>
      <ul>
        <li>
          <span class="font-size-6">disable-maintenance</span>
        </li>
      </ul>
    </li>
  </ul>
</div>

<style scoped>
ul {
  list-style-type: none;
  li {
    margin: 0;
  }
}
</style>
---
transition: slide-up
layout: header-text
---
::header::
<h1 class="font-size-12 font-bold">Add descriptions</h1>

::text::
<div>
  <ul>
    <li class="font-size-6">Add clear descriptions to your feature flags</li>
    <li class="font-size-6">What are they for? Whats the usecase?</li>
  </ul>
</div>
---
transition: slide-left
layout: section
class: text-center font-bold
---
# Manners maketh man 👨‍💼
<span class="font-light"> ( Dont be the one... ) </span>
---
transition: slide-left
layout: header-text
class: font-bold text-size-6
---
::header::
<h1 class="font-size-12 font-bold">Manners maketh man 👨‍💼</h1>

::text::
<ul>
  <li v-click>♻️ ReUse Flags</li>
  <br />
  <li v-click>⌨️ Didn't delete obsolete code</li>
</ul>

<style scoped>
ul {
  list-style-type: none;
  li {
    margin: 0;
  }
}
</style>
---
layout: image
image: /assets/backgrounds/end.jpg
backgroundSize: contain
---
<!-- IMAGE -->
---
layout: section
class: text-center font-bold
---
# How we wanna use Feature Flags? 🤔
---
layout: header-text
---
::header::
<h1 class="font-size-12 font-bold">How we wanna use Feature Flags? 🤔</h1>

::text::
<ul class="font-size-8">
  <li v-click="1">✌️ Environments
    <ul class="ml-5 font-size-6" v-click="2">
      <li> DEV & INT </li>
      <li> PROD </li>
    </ul>
  </li>
  <li v-click="3"> 🚫 Don't touch PROD </li>
  <li v-click="4"> 🛠️ maintenance</li>
  <li v-click="5"> 💩 hits the fan </li>
</ul>

<style scoped>
ul {
  list-style-type: none;
  ul {
    list-style-type: disc;
  }
}
</style>
---
<!--END-->
---
