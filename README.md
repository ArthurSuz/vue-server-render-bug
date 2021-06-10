SSR does not render correctly

ersion
3.0.8

Reproduction link
https://github.com/ArthurSuz/vue-server-render-bug

Steps to reproduce
Clone the git repository. Run npm install and then npm run dev. 

What is expected?
```
<template>
  <div :data-test="test">{{ test }}</div>
</template>

<script setup>
import { computed } from "vue";
const test = computed(() => {
  let data = Math.random();
  console.log("data", data);
  return data;
});
</script>
```
render as
```<div data-test="0.348081003750071">0.348081003750071</div>```
'0.348081003750071' is a random number

What is actually happening?
```<div data-test="0.43971510246716083">0.348081003750071</div>```
This 'data-test' has taken the value of the server and has not changed to the value of the client
