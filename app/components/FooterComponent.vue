<script setup lang="ts">
interface FooterItem {
  title: string;
  text: string;
  iconoEmail: string;
  iconoGit: string;
  iconoLinkedin: string;
  derechos: string;
}
defineProps<{ footer: FooterItem }>();
</script>

<template>
  <footer aria-label="Footer">
    <h2>{{ footer.title }}</h2>
    <p>{{ footer.text }}</p>
    <nav aria-label="Social Network ">
      <img :src="footer.iconoEmail" alt="img-email" />
      <img :src="footer.iconoGit" alt="img-git" />
      <img :src="footer.iconoLinkedin" alt="img-linkedin" />
    </nav>
    <p>{{ footer.derechos }}</p>
  </footer>
</template>
