# vue-html-to-print
A Vuejs3 Mixin that allows you to open a print window of the contents given in a certain id

This package has originated from [vue-html-to-paper](https://github.com/mycurelabs/vue-html-to-paper)

[Demo](https://codepen.io/Niickles/pen/podeVrL)

## Installation
Run the following command
```npm install vue-html-to-print```

Usage inside ```main.js```
```
import { createApp } from 'vue'
import HtmlToPrint from "vue-html-to-print";

const app = createApp(App)

app.use(HtmlToPrint).mount('#app')
```

When imported inside of your main.js file, the mixin is callable from your component
```
<template>
  <div>
    <div>
      <h1>This is a default page</h1>
    </div>
    <!-- The div with the desired contents -->
    <div id="print">
      <h1>I'd like to print this</h1>
    </div>
    <button @click="print"></button>
  </div>
<template>

<script>
  export default {
    methods: {
      async print () {
        // Pass the element id here
        await this.$htmlToPrint('print');
      }
    }
  }
</script>
```

Optionally you can apply different options with each call by defining other options
```
this.$htmlToPrint('print');
```
