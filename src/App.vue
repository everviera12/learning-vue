<script setup>
import Counter from './components/counter.vue';
import Card from './components/ui/card.vue';
import TextRow from './components/ui/text-row.vue';

const TECH_ARTICLES = [
    {
        title: "Microservices with Go & Node",
        text: "Exploring high-performance architectures using Go for heavy lifting and Node.js for API orchestration."
    },
    {
        title: "Secure by Design",
        text: "Implementing advanced security headers and Content Security Policy (CSP) in modern Next.js applications."
    },
    {
        title: "The Monorepo Edge",
        text: "Managing multiple backend services with pnpm workspaces for a more efficient developer experience."
    },
    {
        title: "Scalable Infrastructure",
        text: "How tech giants like Mercado Libre handle millions of requests using Go, Kafka, and Kubernetes."
    },
    {
        title: "Web Accessibility 2026",
        text: "Beyond colors: Building inclusive digital products that meet WCAG AA standards and beyond."
    }
];
</script>

<template>
    <TextRow title="Tech Blog" text="Code & Beyond. Weekly articles about the future of software engineering." />
    
    <div class="row">
        <Card 
            v-for="(post, idx) in TECH_ARTICLES" 
            :key="idx" 
            :title="post.title" 
            :text="post.text"
        />
    </div>
    
</template>