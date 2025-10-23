<script setup lang="ts">


import content from "@/assets/content.json" with { type: "json" };
import '@/assets/estilos.scss';
const headerItems = content.headerItems;
const hero = content.hero;
const experience = content.experience;
const projects = content.projects;
const skills = content.skills;
const education = content.education;
const footer = content.footer;
</script>

<template>
  <HeaderComponent :headerItems="headerItems" />
  <main>
    <HeroComponent :hero="hero" />

    <ExperienceComponent :experience="experience" />

    <ProjectsComponent :projects="projects" />

    <SkillsComponent :skills="skills" />

    <EducationComponent :education="education" />
  </main>
  <FooterComponent :footer="footer" />
</template>
