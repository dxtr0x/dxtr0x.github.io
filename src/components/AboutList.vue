<script setup>
const stats = [
    { label: 'focus', value: 'systems · security tooling' },
    { label: 'core stack', value: 'Rust · Go · C' },
    { label: 'app stack', value: 'Flutter · Tauri' },
    { label: 'frontend', value: 'Vue / Nuxt · React' },
    { label: 'status', value: 'building' },
];
</script>

<template>
<div class="stat-list mono">
    <div v-for="stat in stats" :key="stat.label"><span>{{ stat.label }}</span><span>{{ stat.value }}</span></div>
</div>
</template>
