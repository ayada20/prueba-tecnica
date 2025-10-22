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
  <section class="block" aria-labelledby="education-title">
    <h2 class="title" id="education-title">{{ education.titleEducation }}</h2>
    <ul class="introList">
      <li class="list" v-for="item in education.items" :key="item.title">
        <img class="image" :src="item.icon" :alt="item.title" />
        <div class="intro">
          <h3 class="subtitle">{{ item.title }}</h3>
          <p class="place">{{ item.place }}</p>
          <p class="year">
            <time :datetime="item.yearGraduation">{{
              item.yearGraduation
            }}</time>
          </p>
        </div>
      </li>
    </ul>
  </section>
</template>

<style lang="scss" scoped>
@import "@/assets/estilos.scss";

.block {
  background-color: $background-color;
  padding-bottom: 6em;
}
.title {
  @include flex-center;
  color: $title-color;
  padding-top: 1.5em;
  font-size: 4.8em;
}
.list {
  display: flex;
  width: 100%;
  max-width: 100em;
  border-radius: 2em;
  background-color: $secondary-color;
  margin: 3em;
}
.introList {
  padding: 2em;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.image {
  width: 5.5em;
  height: 6em;
  margin-right: 1em;
  margin-top: 4em;
  margin-left: 3em;
  background-color: $primary-color;
  border-radius: 3em;
  padding: 1em;
}
.intro {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding: 2em;
}

.subtitle {
  color: $title-color;
  font-family: $text-font;
  font-size: 1.7em;
  margin-bottom: 0.5em;
}
.place {
  font-family: $text-font;
  color: $text-color;
  font-size: 1.3em;
  margin-bottom: 1em;
}
.year {
  font-family: $text-font;
  color: $text-color;
  font-size: 1.3em;
  margin-bottom: 1em;
  font-weight: bold;
}

@media (max-width: 50em) {
  .title {
    font-size: 2em;
  }
  .subtitle {
    font-size: 0.8em;
  }
  .place {
    font-size: 0.8em;
  }
  .year {
    font-size: 0.8em;
  }
  .image {
    width: 3em;
    height: 3em;
    margin-top: 3em;
  }
}
</style>
