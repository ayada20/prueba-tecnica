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
    <!--
    <img :src="experience.icon" :alt="experience.mainTitle + ' icon'" />
-->
    <ul>
      <li v-for="item in experience.items" :key="item.title">
        <article>
          <header>
            <h3 class="title">{{ item.title }}</h3>
            <h4 class="subtitle">{{ item.subtitle }}</h4>
          </header>
          <p class="description">{{ item.description }}</p>
        </article>
      </li>
    </ul>
  </section>
</template>

<style lang="scss" scoped>
section {
  background-color: rgb(46, 46, 46);

  padding: 5em;
}
h2 {
  display: flex;
  justify-content: center;
  font-size: 4.3em;
  color: white;

  margin-top: 0.5em;
}
ul {
  list-style: none;
  padding: 1em;
}
.title {
  color: rgb(234, 196, 73);
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  font-size: 1.5em;
  margin-top: 3.5em;
}
.subtitle {
  color: white;
  margin-top: 0.2em;
  font-size: 2.1em;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}
.description {
  color: rgb(155, 166, 176);
  margin-top: 0.7em;
  margin-bottom: 0.6em;
  font-size: 1.7em;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}
</style>
