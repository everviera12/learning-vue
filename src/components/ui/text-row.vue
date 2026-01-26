<script setup>
defineProps({
    title: {
        type: String,
        default: 'No hay titulo'
    },
    text: {
        type: String,
        default: 'Sin descripción'
    },
});
</script>

<template>
    <div class="title">
        <h1> {{ title }} </h1>
        <p>{{ text }}</p>
    </div>
</template>