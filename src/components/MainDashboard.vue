<script setup>
import HeaderDashboard from './HeaderDashboard.vue'
import ThemeDashboard from './ThemeDashboard.vue'
import ResultsDashboard from './ResultsDashboard.vue'

import iconFacebook from '../assets/images/icon-facebook.svg'
import iconTwitter from '../assets/images/icon-twitter.svg'
import iconInstagram from '../assets/images/icon-instagram.svg'
import iconYoutube from '../assets/images/icon-youtube.svg'


const resultsDashboardData =[ 
  {
    id: 1,
    name: '@nathanf',
    image: iconFacebook,
    alt: 'Dashboard facebook icon in social media',
    followersAmount: '1987',
    unit: 'FOLLOWERS',
    followersCount: 12,
    borderColor: 'hsl(208, 92%, 53%)'
  },
  {
    id: 2,
    name: '@nathanf',
    image: iconTwitter,
    alt: 'Dashboard twitter icon in social media',
    followersAmount: '1044',
    unit: 'FOLLOWERS',
    followersCount: 99,
    borderColor: 'hsl(203, 89%, 53%)'
  },
  {
    id: 3,
    name: '@realnathanf',
    image: iconInstagram,
    alt: 'Dashboard facebook instagram in social media',
    followersAmount: '11k',
    unit: 'FOLLOWERS',
    followersCount: 1099,
    borderColor: 'linear-gradient(to right, hsl(37, 97%, 70%), hsl(329, 70%, 58%))'
  },
  {
    id: 4,
    name: 'Natan F',
    image: iconYoutube,
    alt: 'Dashboard facebook youtube in social media',
    followersAmount: '8239',
    unit: 'SUBSCRIBERS',
    followersCount: 144,
    borderColor: 'hsl(348, 97%, 39%)'
  },
]
</script>
<template>
  <header class="dashboard-header-container wrapper">
    <HeaderDashboard />
    <ThemeDashboard />
  </header>
  <ResultsDashboard 
  v-for="dashboardResult in resultsDashboardData" 
  :key="dashboardResult.id"
  :name="dashboardResult.name"
  :src="dashboardResult.image"
  :alt="dashboardResult.alt"
  :followersAmount="dashboardResult.followersAmount"
  :followers="dashboardResult.unit"
  :amount="dashboardResult.followersCount"
  :borderColor="dashboardResult.borderColor"
  />
</template>
<style lang="scss" scoped>
@import '../assets/sass/colors.scss';
@import '../assets/sass/wrapper.scss';
.dashboard-header-container {
  padding-bottom: 1em;
}
@media (min-width: 768px) {
  .dashboard-header-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
}
</style>
