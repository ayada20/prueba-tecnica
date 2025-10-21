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
section {
  background-color: black;
  color: white;
  padding: 5em;
}
h2 {
  display: flex;
  justify-content: center;
  font-size: 4.4em;
  color: white;
  margin-top: 0.7em;
  margin-bottom: 1.2em;
}

ul {
  list-style: none;
  padding: 0;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 2em;
  margin-bottom: 6em;
}

li {
  border-radius: 1.5em;
  background-color: #313133;
  width: 20em;
  height: 33em;

  article {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .image {
    width: 10em;
    height: 10em;
  }

  .titulo {
    padding: 1em;
    font-size: 1.8em;
    text-align: start;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI",
      Roboto, Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue",
      sans-serif;
  }

  .description {
    font-size: 1em;
    color: #666;
    text-align: center;
    margin-bottom: 2em;
    font-size: 1.4em;
    padding: 0.8em;
    text-align: start;
    margin-left: 0.7em;
    color: rgb(155, 166, 176);
  }

  .btn {
    color: rgb(234, 196, 73);
    text-decoration: none;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
    font-weight: bold;
    font-size: 1.4em;
  }
}
</style>
