<script setup lang="ts">
const first = `window.close();`
const second = `window.open('', '_self');
window.close();`
const third = `window.opener = self;
window.close();`
const forth = `window.open('','_self').close();`

function runFirst() {
  window.close();
}

function runSecond() {
  window.open('', '_self');
  window.close();
}

function runThird() {
  window.opener = self;
  window.close();
}

function runForth() {
  window.open('', '_self')!.close();
}
</script>

<template>
  <pre>{{ first }}</pre>
  <button @click="runFirst()">run</button>

  <pre>{{ second }}</pre>
  <button @click="runSecond()">run</button>

  <pre>{{ third }}</pre>
  <button @click="runThird()">run</button>

  <pre>{{ forth }}</pre>
  <button @click="runForth()">run</button>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
