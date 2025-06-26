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
      <h2 class="overview-dashboard-card__title">{{ props.title }}</h2>
      <img class="overview-dashboard-card__icon" :src="props.src" :alt="props.alt" />
      <p class="overview-dashboard-card__amount">{{ props.followersAmount }}</p>
      <div class="overview-dashboard-growth">
        <img :src="props.growthIcon" />
        <p :style="{ color: props.color }">{{ props.growthAmount }}%</p>
      </div>
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
  .overview-dashboard-card{
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: repeat(2, 1fr);
    padding: 0 1.75em;
    &__title{
        color: changeFontColor($dark-grayish-blue);
    }
    &__icon{
         justify-self: end;
    }
    &__amount{
        font-weight: changeFontWeight($bold-font-weight);
        font-size: changeFontSize(2.25rem);
    }
    .overview-dashboard-growth{
        display: flex;
        align-items: center;
        gap: 0 .25em;
        justify-self: end;
    }
  }
}
</style>
