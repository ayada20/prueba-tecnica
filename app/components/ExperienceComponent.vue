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
  <section class="general">
    <h2 class="titleGeneral">{{ experience.mainTitle }}</h2>
    <!--
    <img :src="experience.icon" :alt="experience.mainTitle + ' icon'" />
-->
    <ul class="list">
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
@import "@/assets/estilos.scss";

.general {
  background-color: $secondary-color;
  display: flex;
  flex-direction: column;
  padding: 5em;
}
.titleGeneral {
  @include flex-center;
  font-size: 4.3em;
  color: $title-color;

  margin-top: 0.5em;
}

.title {
  color: $primary-color;
  font-family: $text-font;
  font-size: 1.5em;
  margin-top: 3.5em;
}
.subtitle {
  color: $title-color;
  margin-top: 0.2em;
  font-size: 2.1em;
  font-family: $text-font;
}
.description {
  color: $text-color;
  margin-top: 0.7em;
  margin-bottom: 0.6em;
  font-size: 1.7em;
  font-family: $text-font;
  max-width: 45em;
}

.list {
  display: flex;
  flex-direction: column;
  align-items: center;
  list-style: none;
  padding: 1em;
}

@media (max-width: 50em) {
  .titleGeneral {
    font-size: 2em;
  }

  .title {
    font-size: 0.8em;
  }
  .subtitle {
    font-size: 1em;
  }
  .description {
    font-size: 0.8em;
  }
}
</style>
