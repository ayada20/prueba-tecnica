<script setup lang="ts">
interface ExperienceItem {
  title: string;
  subtitle: string;
  description: string;
}

interface ExperienceData {
  mainTitle: string;
  icon: string;
  items: ExperienceItem[];
}

defineProps<{ experience: ExperienceData }>();
</script>

<template>
  <section>
    <h2>{{ experience.mainTitle }}</h2>
    <img :src="experience.icon" :alt="experience.mainTitle + ' icon'" />

    <ul>
      <li v-for="item in experience.items" :key="item.title">
        <article>
          <header>
            <h3>{{ item.title }}</h3>
            <h4>{{ item.subtitle }}</h4>
          </header>
          <p>{{ item.description }}</p>
        </article>
      </li>
    </ul>
  </section>
</template>
