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

const emit = defineEmits(["pinFavorite"]);
</script>

<template>
    <article class="card my-3 bg-info-subtle" style="width: 18rem; height: 18rem;">
        <div class="card-body d-grid">
            <div>
                <h2 class="card-title fw-light">{{ title }}</h2>
                <p class="card-text"> {{ text }} </p>
            </div>

            <button @click="$emit('pinFavorite', title)"
                class="text-primary fw-medium text-start link-offset-2 bg-transparent border-0 w-50">
                Favorite
            </button>
        </div>
    </article>
</template>
