<script setup lang="ts">
interface NavItem {
  name: string;
  link: string;
}

defineProps<{ headerItems: NavItem[] }>();
</script>

<template>
  <nav aria-label="menu">
    <div class="navbar-list">
      <ul class="lista">
        <li v-for="item in headerItems" :key="item.name">
          <a :href="item.link">{{ item.name }}</a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<style lang="scss" scoped>
@import "@/assets/estilos.scss";

nav {
  background-color: $background-color;
  padding: 1.5em;
  border-bottom: 0.001em solid $primary-color;

  .navbar-list {
    .lista {
      display: flex;
      align-items: center;
      list-style: none;
      padding: 0.8em;

      li {
        a {
          font-weight: bold;
          font-size: 1.2em;
          font-family: $text-font;
          color: $title-color;
          text-decoration: none;
          margin-left: 1.5em;
          &:hover {
            text-decoration: underline;
          }
        }

        &:first-child {
          margin-right: auto;
          a {
            font-size: 2.1em;
            text-decoration: none;
            font-family: $title-font;
            color: $title-color;
          }
        }
      }
    }
  }
}

@media (max-width: 50em) {
  .lista li a {
    display: none;
  }

  .lista li:first-child a {
    display: block;
  }
}
</style>
