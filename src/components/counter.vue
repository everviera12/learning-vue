<script setup>
import { computed, ref } from 'vue';

const counter = ref(0)
const arrayCounter = ref([])

const handleClick = (step) => {
    counter.value += step
}

const buttonClass = computed(() => {
    if (counter.value === 0) return 'neutral'
    if (counter.value < 0) return 'negative'
    return 'positive'
})

const add = () => {
    arrayCounter.value.push(counter.value);
    console.log(arrayCounter.value);
};

const blockNumber = computed(() =>
    arrayCounter.value.includes(counter.value)
)

const sortedArrayCounter = computed(() => {
    return [...arrayCounter.value].sort((a, b) => a - b)
})

</script>

<template>

    <h1> Contador con Bootstrap </h1>
    <h2 :class="counter === 0 ? 'neutral' : counter < 0 ? 'negative' : 'positive'">
        {{ counter }}
    </h2>

    <div class="btn-group">
        <button class="btn btn-success" @click="handleClick(1)">+</button>
        <button class="btn btn-danger" @click="handleClick(-1)">-</button>
        <button @click="add" :disabled="blockNumber" class="btn btn-primary">
            Add
        </button>
    </div>

    <ul class="list-group mt-2">
        <li class="list-group-item" v-for="(item, index) in sortedArrayCounter" :key="index">
            {{ item }}
        </li>
    </ul>
</template>

<style scoped>
h1 {
    color: dodgerblue;
}

.negative {
    color: red;
}

.positive {
    color: lime;
}

.neutral {
    color: white;
}
</style>