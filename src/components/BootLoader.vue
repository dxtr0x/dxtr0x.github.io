<script setup lang="js">
import { ref, onMounted } from 'vue';

// 1. Déclarer des Template Refs (doivent avoir le même nom que l'attribut ref="" dans le template)
const bootEl = ref(null);

// NOTE : Si heroContent est dans un autre composant ou plus haut,
// vous pouvez utiliser un émetteur d'événement ou garder le document.getElementById
// mais STRICTEMENT à l'intérieur de la fonction boot() après le montage.

const lines = [
  { text: '$ whoami', delay: 0 },
  { text: '> palestine — systems / security / full-stack', delay: 400, ok: true },
  { text: '$ uname -a', delay: 250 },
  { text: '> Rust · Go · C · Flutter · Tauri', delay: 400, ok: true },
  { text: '$ ./init --load-profile', delay: 250 },
  { text: '> profile loaded [ok]', delay: 350, ok: true },
];

async function typeLine(el, text, speed = 14){
  for(let i=0; i<text.length; i++){
    el.textContent += text[i];
    await new Promise(r => setTimeout(r, speed));
  }
}

async function boot(){
  const heroContent = document.getElementById('heroContent');

  // En Vue, on accède à l'élément HTML via .value
  const targetBootEl = bootEl.value;
  if (!targetBootEl) return;

  if (window.matchMedia('(prefers-reduced-motion: reduce)').matches){
    targetBootEl.innerHTML = lines.map(l => l.ok ? `<span class="ok">${l.text}</span>` : l.text).join('\n');
    if (heroContent) heroContent.classList.add('show');
    return;
  }

  for(const line of lines){
    await new Promise(r => setTimeout(r, line.delay));
    const lineEl = document.createElement('div');
    if(line.ok) lineEl.className = 'ok';
    targetBootEl.appendChild(lineEl);
    await typeLine(lineEl, line.text);
  }

  const cur = document.createElement('span');
  cur.className = 'cur';
  targetBootEl.appendChild(cur);

  await new Promise(r => setTimeout(r, 500));
  if (heroContent) heroContent.classList.add('show');
}

// 2. Lancer la fonction UNIQUEMENT quand le composant est injecté dans le DOM
onMounted(() => {
  boot();
});
</script>

<template>
    <!-- 3. Remplacement de id="boot" par ref="bootEl" -->
    <div class="boot mono" ref="bootEl" />
</template>
