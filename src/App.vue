<script setup>
console.log("Hello world from console");
const message = 'Hello world dinamyc'
const active = false
const modal = true

const arrayFruits = ['🍑', '🍍', '🍏', '🍉', '🍓', '🍌', '🍊']
</script>

<template>
  <h1>Hello world!</h1>
  <h2>{{ message }}</h2>
  <!-- <h3 :style="`color: red; font-weight: 600;`">{{ active ? 'tamo activo 😎' : 'no tamo activo 😖' }}</h3> -->
  
  <!-- directivas -->
  <h3 v-if="active">tamo activo con directivas 😎</h3>
  <h3 v-else="active">no tamo activo con directivas 😖</h3>

  <h4 v-show="modal" style="color: yellow;"> v-show {{ modal }}</h4>
</template>

<style>
h1 {
  color: dodgerblue;
}
</style>