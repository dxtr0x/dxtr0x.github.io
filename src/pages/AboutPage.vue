<script setup>
import { shallowRef } from 'vue';
import SectionContainer from '@/components/SectionContainer.vue';
import AboutText from '@/components/AboutText.vue';
import AboutList from '@/components/AboutList.vue';

const aboutText = shallowRef(AboutText);
const aboutList = shallowRef(AboutList);

</script>

<template>
<div id="about" style="border-top:none;">
    <SectionContainer
        Counter_Section="01"
        Section_title="About"
        :content="[aboutText,aboutList]"
    />
</div>
</template>
