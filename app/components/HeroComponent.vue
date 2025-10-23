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
  <section class="general">
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
@import "@/assets/estilos.scss";

.general {
  background-color: $background-color;
  color: $title-color;
  padding: 9em;
}
.imagen {
  display: block;
  margin: auto;
  width: 15em;
  border-radius: 9em;
  border: solid 0.01em $primary-color;
}

.titulo {
  color: $title-color;
  font-family: $title-font;
  font-size: 5.2em;
}
.information {
  padding: 5.5em;
  margin-left: 3em;
}
.subtitulo {
  color: $primary-color;
  font-family: $title-font;
  font-style: italic;
  font-size: 2.8em;
  margin-top: 0.5em;
  margin-bottom: 0.5em;
}

.texto {
  color: $text-color;
  font-family: $text-font;
  font-size: 1.7em;
  padding-right: 3em;
  margin-bottom: 0.7em;
  max-width: 40em;
}
.btn {
  background-color: $primary-color;
  color: $background-color;

  border-radius: 0.5em;
  padding: 1em 2.5em;
  font-weight: bold;
  font-size: 1.6em;
  margin-top: 1.2em;

  &:hover {
    background-color: $text-color;
    color: $primary-color;
  }
}

@media (max-width: 50em) {
  .imagen {
    max-width: 3em;
  }

  .titulo {
    font-size: 2em;
    text-align: center;
  }

  .information {
    padding: 1em;
    margin: 0;
  }

  .subtitulo {
    font-size: 1.5em;
  }

  .texto {
    font-size: 1em;
  }

  .btn {
    font-size: 1em;
  }
}
</style>
