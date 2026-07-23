<script setup>
const name = "Salah Ahmed Yasser"
const knowledges = ["systems programming", "full‑stack development", "security tooling"]
const languages = ["Rust", "Go", "C/C++"]
</script>

<template>
  <p class="lede">
    I’m <b>{{ name }}</b> — I work across
    <!-- Knowledges list -->
    <span v-for="(knowledge, i) in knowledges" :key="i">
      <b>{{ knowledge }}</b>
      <template v-if="i === knowledges.length - 2">
        <!-- Oxford “and” before the final item -->
        <span>, and </span>
      </template>
      <template v-else-if="i < knowledges.length - 1">
        <!-- Regular comma for the others -->
        <span>, </span>
      </template>
    </span>.
    Comfortable at the bottom of the stack in

    <!-- Languages list -->
    <span v-for="(lang, i) in languages" :key="i">
      <b>{{ lang }}</b>
      <template v-if="i === languages.length - 2">
        <span>, and </span>
      </template>
      <template v-else-if="i < languages.length - 1">
        <span>, </span>
      </template>
    </span>.
  </p>
</template>
