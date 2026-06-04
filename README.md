# VCalendar Plugin for Vue 3

> **SiteMinder fork** (`@siteminder/v-calendar`) of [nathanreyes/v-calendar](https://github.com/nathanreyes/v-calendar).
> Upstream is effectively unmaintained; this fork adds defensive guards so the
> calendar/date picker works under Vue 3.5. See [CHANGELOG.md](CHANGELOG.md) for
> fork-specific changes. The usage docs below still apply (see also https://vcalendar.io).

A calendar and date picker plugin for [Vue.js](https://vuejs.org).

[Vue.js](https://vuejs.org) 3.2+ (3.5 supported), [Popper.js](https://popper.js.org/docs/v2/) 2.0+ are required.

## Install Plugin

### NPM

```shell
npm install @siteminder/v-calendar @popperjs/core
```

### Yarn

```shell
yarn add @siteminder/v-calendar @popperjs/core
```

## Use Plugin

:warning: **As of `v3.0.0-alpha.7`, all installation methods require manual import of component styles. This is due to Vite build restrictions in libary mode.**

```js
import 'v-calendar/style.css';
```

### Method 1: Use Globally

```js
import VCalendar from 'v-calendar';
import 'v-calendar/style.css';

// Use plugin with optional defaults
app.use(VCalendar, {})
```

```html
<!-- MyComponent.vue -->
<template>
  <VCalendar />
  <VDatePicker v-model="date" />
</template>
```

### Method 2: Use Components Globally

```js
// main.js
import { setupCalendar, Calendar, DatePicker } from 'v-calendar';
import 'v-calendar/style.css';

// Use plugin defaults (optional)
app.use(setupCalendar, {})

// Use the components
app.component('VCalendar', Calendar)
app.component('VDatePicker', DatePicker)
```

```html
<!-- MyComponent.vue -->
<template>
  <VCalendar />
  <VDatePicker v-model="date" />
</template>
```

### Method 3: Use Components As Needed

```js
// main.js
import { setupCalendar } from 'v-calendar';

// Use calendar defaults (optional)
app.use(setupCalendar, {})
```

```vue
<!-- MyComponent.vue -->
<template>
  <Calendar />
  <DatePicker v-model="date">
</template>

<script>
import { Calendar, DatePicker } from 'v-calendar';
import 'v-calendar/style.css';

export default {
  components: {
    Calendar,
    DatePicker,
  },
  data() {
    return {
      date: new Date(),
    };
  },
}
</script>
```

## Source setup

Please follow below mentioned steps to clone and build this project:

### Clone the repo

```sh
git clone https://github.com/nathanreyes/v-calendar

# Move to directory
cd v-calendar
```

### Install dependencies

```sh
yarn
```

### Build library

```sh
# Types, ES, ESM, CommonJS, IIFE
yarn build
```

### Lint and fix files

```sh
yarn lint
```

### Test library

```sh
# Types, ES, ESM, CommonJS, IIFE
yarn test
```