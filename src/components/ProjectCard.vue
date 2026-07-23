<script setup>

defineProps({
  projects: {
    type: Array,
    required: true,
  },
});
</script>
<template>
<div v-for="(proj, index) in projects" :key="proj.title">
<div class="proj">
  <div class="proj-top">
    <div>
      <div class="proj-num mono">0{{ index + 1 }}</div>
      <h3><a href="#" target="_blank">{{ proj.title }} ↗</a></h3>
      <div class="role mono">{{ proj.role }}</div>
    </div>
  </div>
  <p>{{ proj.description }}</p>
  <div class="tags mono">
    <span v-for="tag in proj.tags" :key="tag">{{ tag }}</span>
    </div>
</div>
</div>
</template>
