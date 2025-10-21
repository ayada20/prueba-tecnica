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
      <ul>
        <li v-for="item in headerItems" :key="item.name">
          <a :href="item.link">{{ item.name }}</a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<style lang="scss" scoped>
nav {
  background-color: black;
  padding: 1em;
  border-bottom: 0.001em solid rgb(223, 194, 65);

  .navbar-list {
    ul {
      display: flex;
      align-items: center;
      list-style: none;
      padding: 0.8em;

      li {
        a {
          font-weight: bold;
          font-size: 1.2em;
          font-family: Arial, Helvetica, sans-serif;
          color: rgb(214, 207, 207);
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
            font-family: serif;
            color: rgb(214, 207, 207);
          }
        }
      }
    }
  }
}
</style>
