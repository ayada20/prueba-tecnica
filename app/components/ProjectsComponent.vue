<script setup lang="ts">
interface ProjectItem {
  image: string;
  title: string;
  decription: string;
  linkText: string;
}
interface ProjectsData {
  mainTitleProjects: string;
  items: ProjectItem[];
}

defineProps<{ projects: ProjectsData }>();
</script>

<template>
  <section aria-labelledby="projects-title">
    <h2 id="projects-title">{{ projects.mainTitleProjects }}</h2>
    <ul>
      <li v-for="item in projects.items" :key="item.title">
        <article>
          <img :src="item.image" :alt="item.title" />
          <h3>{{ item.title }}</h3>
          <p>{{ item.decription }}</p>
          <a :href="item.linkText">{{ item.linkText }}</a>
        </article>
      </li>
    </ul>
  </section>
</template>
