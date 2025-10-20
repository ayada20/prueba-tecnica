<script setup lang="ts">
interface HeroData {
  image: string;
  title: string;
  subtitle: string;
  description: string;
  buttonText:string;
}

import content from "@/assets/content.json" with { type: "json" };

const hero = content.hero as HeroData;
</script>

<template>
  <section>
    <img :src="hero.image" alt="profil image  {{ hero.title }}" />
    <h1>{{ hero.title }}</h1>
    <h2>{{ hero.subtitle }}</h2>
    <p>{{ hero.description }}</p>
    <button type="button">{{ hero.buttonText }}</button>
  </section>
</template>
