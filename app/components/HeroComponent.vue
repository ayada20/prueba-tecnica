<script setup lang="ts">
interface HeroData {
  image: string;
  title: string;
  subtitle: string;
  description: string;
  buttonText: string;
}

defineProps<{ hero: HeroData }>();
</script>

<template>
  <section>
    <img class="imagen" :src="hero.image" :alt="hero.title" />
    <div class="information">
      <h1 class="titulo">{{ hero.title }}</h1>

      <h2 class="subtitulo">{{ hero.subtitle }}</h2>
      <p class="texto">{{ hero.description }}</p>
      <button class="btn" type="button">{{ hero.buttonText }}</button>
    </div>
  </section>
</template>

<style lang="scss" scoped>
section {
  background-color: black;
  color: white;
  padding: 4em;
}
.imagen {
  display: block;
  margin: auto;
  padding-top: 6em;

  border-radius: 2em;
  max-width: 18em;
}

.titulo {
  color: rgb(227, 227, 227);
  font-family: serif;
  font-size: 5.2em;
}
.information {
  padding: 5em;
}
.subtitulo {
  color: rgb(198, 163, 49);
  font-family: serif;
  font-style: italic;
  font-size: 2.8em;
  margin-top: 0.5em;
  margin-bottom: 0.5em;
}

.texto {
  color: rgb(131, 141, 152);
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  font-size: 1.7em;
  padding-right: 3em;
  margin-bottom: 0.7em;
}
.btn {
  background-color: rgb(198, 163, 49);
  color: black;

  border-radius: 0.5em;
  padding: 1em 2.5em;
  font-weight: bold;
  font-size: 1.6em;
  margin-top: 1.2em;

  &:hover {
    background-color: rgb(201, 173, 81);
  }
}
</style>
