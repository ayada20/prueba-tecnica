<script setup lang="ts">
interface EducationItem {
  icon: string;
  title: string;
  place: string;
  yearGraduation: string;
}

interface EducationData {
  titleEducation: string;
  items: EducationItem[];
}

defineProps<{ education: EducationData }>();
</script>

<template>
  <section aria-labelledby="education-title">
    <h2 id="education-title">{{ education.titleEducation }}</h2>
    <ul>
      <li v-for="item in education.items" :key="item.title">
        <span><img :src="item.icon" :alt="item.title" /></span>
        <div>
          <h3>{{ item.title }}</h3>
          <p>{{ item.place }}</p>
          <p>
            <time :datetime="item.yearGraduation">{{
              item.yearGraduation
            }}</time>
          </p>
        </div>
      </li>
    </ul>
  </section>
</template>
