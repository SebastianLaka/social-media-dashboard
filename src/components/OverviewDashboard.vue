<script setup>
const props = defineProps({
  title: String,
  src: {
    type: String,
    required: true,
  },
  followersCount: Number,
  growthIcon: {
    type: String,
    required: false,
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
