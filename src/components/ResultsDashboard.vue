<script setup>
import { ref } from 'vue'
import ResultsCard from './ResultsCard.vue'
import iconFacebook from '../assets/images/icon-facebook.svg'
import iconTwitter from '../assets/images/icon-twitter.svg'
import iconInstagram from '../assets/images/icon-instagram.svg'
import iconYoutube from '../assets/images/icon-youtube.svg'
import iconUp from '../assets/images/icon-up.svg'
import iconDown from '../assets/images/icon-down.svg'

const resultsDashboardData = ref([
  {
    id: 1,
    name: '@nathanf',
    image: iconFacebook,
    alt: 'Dashboard facebook icon in social media',
    followersAmount: 1987,
    unit: 'FOLLOWERS',
    followersCount: 12,
    borderColor: 'hsl(208, 92%, 53%)',
    growthIcon: iconUp,
    color: 'hsl(163, 72%, 41%)',
  },
  {
    id: 2,
    name: '@nathanf',
    image: iconTwitter,
    alt: 'Dashboard twitter icon in social media',
    followersAmount: 1044,
    unit: 'FOLLOWERS',
    followersCount: 99,
    borderColor: 'hsl(203, 89%, 53%)',
    growthIcon: iconUp,
    color: 'hsl(163, 72%, 41%)',
  },
  {
    id: 3,
    name: '@realnathanf',
    image: iconInstagram,
    alt: 'Dashboard facebook instagram in social media',
    followersAmount: 11000,
    unit: 'FOLLOWERS',
    followersCount: 1099,
    borderColor: 'linear-gradient(to right, hsl(37, 97%, 70%), hsl(329, 70%, 58%))',
    growthIcon: iconUp,
    color: 'hsl(163, 72%, 41%)',
  },
  {
    id: 4,
    name: 'Natan F',
    image: iconYoutube,
    alt: 'Dashboard facebook youtube in social media',
    followersAmount: 8239,
    unit: 'SUBSCRIBERS',
    followersCount: 144,
    borderColor: 'hsl(348, 97%, 39%)',
    growthIcon: iconDown,
    color: 'hsl(356, 69%, 56%)',
  },
])
</script>
<template>
  <section class="dashboard-results wrapper">
    <ResultsCard
      v-for="dashboardResult in resultsDashboardData"
      :key="dashboardResult.id"
      :name="dashboardResult.name"
      :src="dashboardResult.image"
      :alt="dashboardResult.alt"
      :followersAmount="dashboardResult.followersAmount"
      :followers="dashboardResult.unit"
      :amount="dashboardResult.followersCount"
      :borderColor="dashboardResult.borderColor"
      :growthIcon="dashboardResult.growthIcon"
      :color="dashboardResult.color"
    />
  </section>
</template>
<style lang="scss" scoped>
@import '../assets/sass/colors.scss';
@import '../assets/sass/fonts.scss';
@import '../assets/sass/mixins.scss';
.dashboard-results {
  @include flex-center;
  flex-direction: column;
  padding: 0.25em;
  gap: 2em;
}
@media (min-width: 350px) and (max-width: 768px) {
  .dashboard-results {
    display: flex;
  }
}
@media (min-width: 768px) {
  .dashboard-results {
    @include grid-two-columns;
    gap: 2em;
  }
}
@media (min-width: 1200px) {
  .dashboard-results {
    @include grid-four-columns;
  }
}
</style>
