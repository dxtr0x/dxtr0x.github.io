<script setup lang="js">
  const links = [
    { text: 'about', href: '#about' },
    { text: 'work', href: '#work' },
    { text: 'blog', href: 'blog.html' },
    { text: 'interests', href: '#interests' },
    { text: 'contact', href: '#contact' },
  ];
</script>
<template>
<header>
    <div class="nav">
        <div class="prompt mono"><span class="path"></span>dxtr0x</div>
        <ul class="mono">
            <li v-for="link in links" :key="link.href"><a :href="link.href">{{ link.text }}</a></li>
        </ul>
    </div>
</header>
</template>
