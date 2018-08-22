# VueJS Eventbus Plugin

[![awesome-vue](https://img.shields.io/badge/Vue.js-AWESOME-ff69b4.svg)](//github.com/vuejs/awesome-vue)
[![license](https://img.shields.io/github/license/fffixed/vue-bus.svg)](//opensource.org/licenses/MIT)

## Introduction

A simple global event-bus plugin for [VueJS](//vuejs.org) (>= 2.0).

This plugin implements [Non Parent-Child Communication](//vuejs.org/v2/guide/components.html#Non-Parent-Child-Communication).

## Installation

```bash
$ npm i
```

Download and use with your build system
```javascript
import VueBus from 'vue-bus'
// ... maybe ...
var VueBus = require('vue-bus')

// ...  and  ...

Vue.use(VueBus)
```
Or just include it with a script tag
```html
<script src="/vue-bus.js"></script>
```
:sparkles:

## Usage
direct way:
```javascript
// in component A's method
this.$bus.$emit('my-event', 1)

// in component B's created hook
this.$bus.$on('my-event', function(arg) {
  // ...
})
```

magic way:
```javascript
// in component A's method
this.$bus=['my-event', 1]

// in component B create $bus option
methods: { /* ... */ },
$bus: {
  'my-event': function(arg) {
    // ...
  }
}
```

## License
[MIT](//opensource.org/licenses/MIT)

Copyright (c) 2017 fffixed
