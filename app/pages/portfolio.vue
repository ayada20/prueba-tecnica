<script setup lang="ts">

import content from "@/assets/content.json" with { type: "json" };
const experience = content.experience;
const projects = content.projects;
const skills = content.skills;
const education = content.education;
const footer = content.footer;
</script>

<template>
  <HeaderComponent />
  <main>
    <HeroComponent />

    <ExperienceComponent :experience="experience" />

    <ProjectsComponent :projects="projects" />

    <SkillsComponent :skills="skills" />

    <EducationComponent :education="education" />
  </main>
  <FooterComponent :footer="footer" />
</template>
