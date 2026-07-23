<script setup>
import ProjectCard from "@/components/ProjectCard.vue";
import SectionContainer from "@/components/SectionContainer.vue";

const projects = [
  {
    title: "CoreSOC",
    role: "SOC / SIEM analyzer platform",
    description: "A full SOC/SIEM monorepo built on Rust, Go, and React — Sigma rule matching, MITRE<br>ATT&CK tagging, multi-source ingestion, tiered ClickHouse/Parquet storage, alert<br>correlation, and RBAC. Frontend in Nuxt 3 with a dark navy/purple design system:dashboard, Sigma rules editor, ingestion pipeline view, and investigation triage.",
    tags: ["Rust", "Go", "Nuxt 3", "ClickHouse", "Sigma"],
  },
  {
    title: "Oreon ↗",
    role: "peer‑to‑peer messaging, Flutter / Android",
    description: "A peer-to-peer messaging app that routes over Bluetooth and Wi-Fi transport layers instead of relying on a central server. Includes a hardened WebSocket chat service (singleton lifecycle, stream controller disposal, type-cast fixes) and a manifest hardened for BLE/Wi-Fi mesh networking — TLS enforcement, explicit service exports, data extraction rules.",
    tags: ["Flutter", "Android", "Bluetooth", "Wi‑Fi mesh", "security"],
  },
];

const workContent = ProjectCard.props.projects;
</script>

<template>
  <div class="work">
    <!-- Pass the whole array as a prop called “container” -->
    <SectionContainer
      Counter_Section="02"
      Section_title="Work"
      :container="[]"
     />
      <ProjectCard :projects="projects" />
  </div>
</template>
