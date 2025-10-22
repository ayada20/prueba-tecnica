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
  <footer class="footer" aria-label="Footer">
    <h2 class="title">{{ footer.title }}</h2>
    <p class="paraghraph">{{ footer.text }}</p>
    <nav class="images" aria-label="Social Network ">
      <img class="image" :src="footer.iconoEmail" alt="img-email" />
      <img class="image" :src="footer.iconoGit" alt="img-git" />
      <img class="image" :src="footer.iconoLinkedin" alt="img-linkedin" />
    </nav>
    <p class="paraghraph">{{ footer.derechos }}</p>
  </footer>
</template>

<style lang="scss" scoped>
@import "@/assets/estilos.scss";
.footer {
  background-color: rgb(33, 37, 43);
  padding: 9em;
}
.title {
  color: $title-color;
  @include flex-center;
  font-size: 4em;
}
.paraghraph {
  @include flex-center;
  color: $text-color;
  font-family: $text-font;
  font-size: 1.5em;
  padding: 1.5em;
}
.images {
  @include flex-center;
}
.image {
  width: 6em;
  height: 6em;
  padding: 1em;

  &:hover {
    background-color: $text-color;
    border-radius: 5em;
  }
}

@media (max-width: 50em) {
  .title {
    font-size: 2em;
  }
  .paraghraph {
    font-size: 1em;
  }
  .image {
    width: 4em;
    height: 4em;
  }
}
</style>
