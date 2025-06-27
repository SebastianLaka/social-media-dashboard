<script setup>
import { computed } from 'vue'
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
const convertAtKValues = computed(() => {
  if (props.followersAmount > 10000) {
    return (props.followersAmount / 1000).toFixed(0) + 'k'
  } else {
    return props.followersAmount
  }
})
</script>
<template>
  <div class="overview-dashboard-card">
    <h2 class="overview-dashboard-card__title">{{ props.title }}</h2>
    <img class="overview-dashboard-card__image" :src="props.src" :alt="props.alt" />
    <p class="overview-dashboard-card__amount">{{ convertAtKValues }}</p>
    <div class="overview-dashboard-growth">
      <img class="overview-dashboard-growth__icon" :src="props.growthIcon" />
      <p class="overview-dashboard-growth__amount" :style="{ color: props.color }">{{ props.growthAmount }}%</p>
    </div>
  </div>
</template>
<style lang="scss" scoped>
@import '../assets/sass/colors.scss';
@import '../assets/sass/fonts.scss';
.overview-dashboard-card {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: repeat(2, 1fr);
  padding: 1em;
  gap: .5em;
  &__title {
    color: changeFontColor($dark-grayish-blue);
  }
  &__image {
    justify-self: end;
  }
  &__amount {
    font-weight: changeFontWeight($bold-font-weight);
    font-size: changeFontSize(2.25rem);
  }
  .overview-dashboard-growth {
    display: flex;
    align-items: center;
    gap: 0 0.25em;
    justify-self: end;
    &__amount{
        font-weight: changeFontWeight($bold-font-weight);
    }
  }
}
@media (min-width: 350px) and (max-width: 768px) {
  .overview-dashboard-card {
    width: 75%;
  }
}
</style>
