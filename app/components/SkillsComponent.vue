<script setup lang="ts">
interface TechnicalSkill {
  name: string;
}

interface SoftSkill {
  icon: string;
  name: string;
}

interface SkillsData {
  generalTitle: string;
  titleTechnical: string;
  titleSoft: string;
  technicalSkills: TechnicalSkill[];
  softSkills: SoftSkill[];
}

defineProps<{ skills: SkillsData }>();
</script>
<template>
  <section>
    <h2 class="general-title">{{ skills.generalTitle }}</h2>
    <div class="packTitles">
      <h3 id="skills-technical-title">{{ skills.titleTechnical }}</h3>
      <h4 id="skills-soft-title">{{ skills.titleSoft }}</h4>
    </div>
    <div class="packInfo">
      <ul>
        <li
          class="techSkills"
          v-for="skill in skills.technicalSkills"
          :key="skill.name"
        >
          {{ skill.name }}
        </li>
      </ul>

      <ul>
        <li v-for="skill in skills.softSkills" :key="skill.name">
          <img class="image" :src="skill.icon" :alt="skill.icon" />
          <span class="titleSoft">{{ skill.name }}</span>
        </li>
      </ul>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@import "@/assets/estilos.scss";

section {
  background-color: $secondary-color;
}
.general-title {
  @include flex-center;
  color: $title-color;
  padding-top: 1.5em;
  font-size: 4.5em;
}
.packTitles {
  @include flex-center;
}

h3,
h4 {
  font-size: 3.5em;
  padding: 1.5em;
  color: $title-color;
}
ul {
  max-width: 45em;
}

li {
  display: inline-flex;
  gap: 1em;
  border: 0.01em solid $primary-color;
  margin: 1em;
  padding: 1em;
  border-radius: 1em;
  list-style: none;
  font-weight: bold;
  font-family: $text-font;
}
.packInfo {
  @include flex-center;
  align-items: center;
  padding-bottom: 9em;
}
.image {
  width: 2em;
  height: 2em;
}
.titleSoft {
  color: $title-color;
  font-size: 1.3em;
  font-weight: bold;
  font-family: $text-font;
  margin: 0.5;

  &:hover {
    color: $primary-color;
  }
}
.techSkills {
  color: $primary-color;
  font-size: 1.4em;
  &:hover {
    background-color: $primary-color;
    color: $secondary-color;
  }
}

@media (max-width: 50em) {
  .packTitles {
    font-size: 0.4em;
  }
  .techSkills {
    font-size: 0.7em;
  }
  .titleSoft {
    font-size: 0.8em;
  }
  .image {
    width: 0.5em;
    height: 0.5em;
  }
  .general-title {
    font-size: 2em;
  }
}
</style>
