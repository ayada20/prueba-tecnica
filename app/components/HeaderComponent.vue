<script setup lang="ts">
interface NavItem {
  name: string;
  link: string;
}

import content from "@/assets/content.json" with { type: "json" };

const items = content.navItems as NavItem[];
</script>

<template>
  <nav aria-label="menu">
    <ul>
      <li v-for="item in items" :key="item.link">
        <a :href="item.link">{{ item.name }}</a>
      </li>
    </ul>
  </nav>
</template>
