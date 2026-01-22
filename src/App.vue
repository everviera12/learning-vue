<script setup>
import { ref } from 'vue';

console.log("Hello world from console");

const message = 'Hello world dinamyc';
const active = false;
const modal = true;


const counter = ref(0)

const handleClick = (condition) => {
  if (condition === true) {
    counter.value++
  } else {
    counter.value--
  }
  console.log(counter.value)
}


const arrayFruits = [
  {
    name: "Manzana",
    icon: '🍎',
    price: "$1.00",
    description: "Una manzana",
    stock: 0,
  },
  {
    name: "Pera",
    icon: '🍐',
    price: "$2.00",
    description: "Una pera",
    stock: 10,
  },
  {
    name: "Naranja",
    icon: '🍊',
    price: "$3.00",
    description: "Una naranja",
    stock: 20,
  },
]
</script>

<template>
  <h1>Hello world!</h1>
  <h2>{{ message }}</h2>
  <!-- <h3 :style="`color: red; font-weight: 600;`">{{ active ? 'tamo activo 😎' : 'no tamo activo 😖' }}</h3> -->

  <!-- directivas -->
  <h3 v-if="active">tamo activo con directivas 😎</h3>
  <h3 v-else="active">no tamo activo con directivas 😖</h3>

  <h4 v-show="modal" style="color: yellow;"> v-show {{ modal }}</h4>

  <ol>
    <template v-for="(fruit, idx) in arrayFruits" :key="idx">
      <li v-if="fruit.stock > 0">
        {{ fruit.icon }} - {{ fruit.price }} - {{ fruit.name }}
      </li>
    </template>
  </ol>

  <h2 :class="counter < 0 ? 'negative' : 'positive'">
    {{ counter }}
  </h2>

  <div style="display: flex; gap: 1rem;">
    <button @click="handleClick(true)">Button +</button>
    <button @click="handleClick(false)">Button -</button>
  </div>



  <!-- <button v-on:click="handleClick()">Activo 1</button>
  <button @click.right="handleClick()">Activo 2</button> -->
</template>

<style>
h1 {
  color: dodgerblue;
}

.negative {
  color: red;
}

.positive { 
  color: lime;
}
</style>