<script setup lang="ts">
interface TechnicalSkill {
  name: string;
}

interface SoftSkill {
  icon: string;
  name: string;
}

interface SkillsData {
  titleTechnical: string;
  titleSoft: string;
  technicalSkills: TechnicalSkill[];
  softSkills: SoftSkill[];
}

defineProps<{ skills: SkillsData }>();
</script>
<template>
  <section aria-labelledby="skills-technical-title">
    <h2 id="skills-technical-title">{{ skills.titleTechnical }}</h2>
    <ul>
      <li v-for="skill in skills.technicalSkills" :key="skill.name">
        {{ skill.name }}
      </li>
    </ul>

    <h2 id="skills-soft-title">{{ skills.titleSoft }}</h2>
    <ul>
      <li v-for="skill in skills.softSkills" :key="skill.name">
        <img :src="skill.icon" :alt="skill.icon" />
        <span>{{ skill.name }}</span>
      </li>
    </ul>
  </section>
</template>
