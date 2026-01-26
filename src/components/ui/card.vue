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
    <article class="card bg-info-subtle" style="width: 18rem; height: 18rem;">
        <div class="card-body d-grid">
            <div>
                <h2 class="card-title fw-light">{{ title }}</h2>
                <p class="card-text"> {{ text }} </p>
            </div>

            <a href="#" class="text-primary fw-medium link-offset-2">
                View more
            </a>
        </div>
    </article>
</template>
