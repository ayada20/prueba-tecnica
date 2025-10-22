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
  <section class="general" aria-labelledby="projects-title">
    <h2 class="title" id="projects-title">{{ projects.mainTitleProjects }}</h2>

    <ul class="listaGeneral">
      <li class="lista" v-for="item in projects.items" :key="item.title">
        <article class="block">
          <img class="image" :src="item.image" :alt="item.title" />
          <h3 class="titulo">{{ item.title }}</h3>
          <p class="description">{{ item.decription }}</p>
          <a class="btn" :href="'#'">{{ item.linkText }}</a>
        </article>
      </li>
    </ul>
  </section>
</template>
<style lang="scss" scoped>
@import "@/assets/estilos.scss";

.general {
  background-color: $background-color;
  color: $title-color;
  padding: 5em;
}
.title {
  @include flex-center;
  font-size: 4.4em;
  color: $title-color;
  margin-top: 0.7em;
  margin-bottom: 1.2em;
}

.listaGeneral {
  list-style: none;
  @include flex-center;
  flex-wrap: wrap;
  gap: 10em;
  margin-bottom: 6em;
}

.lista {
  border-radius: 1.5em;
  background-color: $secondary-color;
  width: 22em;
  height: 35em;
}
.block {
  @include flex-center;
  flex-direction: column;
  align-items: center;
}

.image {
  width: 21.9em;
  height: 12em;
}

.titulo {
  padding: 1em;
  font-size: 1.8em;
  font-family: $text-font;
  white-space: pre-line;
}

.description {
  color: $text-color;
  margin-bottom: 2em;
  font-size: 1.4em;
  padding: 0.8em;
  text-align: start;
  margin-left: 0.7em;
}

.btn {
  color: $primary-color;
  text-decoration: none;
  font-family: $text-font;
  font-weight: bold;
  font-size: 1.6em;

  &:hover {
    color: $text-color;
  }
}

@media (max-width: 50em) {
  .title {
    font-size: 2em;
  }
  .image {
    width: 14.9em;
    height: 6em;
  }

  .titulo {
    font-size: 1em;
  }

  .description {
    font-size: 1em;
  }

  .btn {
    font-size: 1em;
  }
  .lista {
    width: 15em;
    height: 20em;
  }
}
</style>
