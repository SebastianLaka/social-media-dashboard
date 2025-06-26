<script setup>
const props = defineProps({
  title: String,
  src: {
    type: String,
    required: true,
  },
  alt: String,
  followersAmount: Number,
  growthIcon: {
    type: String,
    required: true,
  },
  growthAmount: Number,
  color: {
    type: String,
    default: 'transparent',
  },
})
</script>
<template>
  <section class="overview-dashboard">
    <h1 class="overview-dashboard__header">Overview - Today</h1>
    <div class="overview-dashboard-card">
        <h2>{{ props.title }}</h2>
        <img :src="props.src" :alt="props.alt"/>
        <p>{{ props.followersAmount }}</p>
        <img :src="props.growthIcon" />
        <p>{{ props.growthAmount }} %</p>
    </div>
  </section>
</template>
<style lang="scss" scoped>
@import '../assets/sass/colors.scss';
@import '../assets/sass/fonts.scss';
.overview-dashboard {
  padding: 0 0.25em;
  &__header {
    font-weight: changeFontWeight($bold-font-weight);
    color: changeFontColor($dark-grayish-blue);
    font-size: changeFontSize(1.75rem);
  }
}
</style>
