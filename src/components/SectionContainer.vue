<script setup>
defineProps({
  Counter_Section: {
    type: Number,
    required : true
    },
  Section_title: {
    type: String,
    required : true
    },
  content: {
    type: Array,
    required : true
  }
})
</script>

<template>
<div id="about">
    <div class="sec-head"><span class="tag mono">{{Counter_Section}}</span><h2>{{Section_title}}</h2></div>
    <div class="about-grid">
        <component
            v-for="(ComponentFile,index) in content"
            :key="index"
            :is="ComponentFile"
        />
    </div>
</div>
</template>
