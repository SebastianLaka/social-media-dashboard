<script setup>
import OverviewCard from './OverviewCard.vue'
import iconFacebook from '../assets/images/icon-facebook.svg'
import iconTwitter from '../assets/images/icon-twitter.svg'
import iconInstagram from '../assets/images/icon-instagram.svg'
import iconYoutube from '../assets/images/icon-youtube.svg'
import iconUp from '../assets/images/icon-up.svg'
import iconDown from '../assets/images/icon-down.svg'
import { ref } from 'vue'
const overviewDashboardData = ref([
  {
    id: 1,
    title: 'Page Views',
    icon: iconFacebook,
    description: 'Facebook icon',
    followersAmount: 87,
    growthIcon: iconUp,
    growthAmount: 3,
    color: 'hsl(163, 72%, 41%)',
  },
  {
    id: 2,
    title: 'Likes',
    icon: iconFacebook,
    description: 'Facebook icon',
    followersAmount: 52,
    growthIcon: iconDown,
    growthAmount: 2,
    color: 'hsl(356, 69%, 56%)',
  },
  {
    id: 3,
    title: 'Likes',
    icon: iconInstagram,
    description: 'Instagram icon',
    followersAmount: 5462,
    growthIcon: iconUp,
    growthAmount: 2257,
    color: 'hsl(163, 72%, 41%)',
  },
  {
    id: 4,
    title: 'Profile Views',
    icon: iconInstagram,
    description: 'Instagram icon',
    followersAmount: 52000,
    growthIcon: iconUp,
    growthAmount: 1375,
    color: 'hsl(163, 72%, 41%)',
  },
  {
    id: 5,
    title: 'Reweets',
    icon: iconTwitter,
    description: 'Twitter icon',
    followersAmount: 117,
    growthIcon: iconUp,
    growthAmount: 303,
    color: 'hsl(163, 72%, 41%)',
  },
  {
    id: 6,
    title: 'Reweets',
    icon: iconTwitter,
    description: 'Twitter icon',
    followersAmount: 507,
    growthIcon: iconUp,
    growthAmount: 553,
    color: 'hsl(163, 72%, 41%)',
  },
  {
    id: 7,
    title: 'Likes',
    icon: iconYoutube,
    description: 'Youtube icon',
    followersAmount: 107,
    growthIcon: iconDown,
    growthAmount: 19,
    color: 'hsl(356, 69%, 56%)',
  },
  {
    id: 8,
    title: 'Total Views',
    icon: iconYoutube,
    description: 'Youtube icon',
    followersAmount: 1407,
    growthIcon: iconDown,
    growthAmount: 12,
    color: 'hsl(356, 69%, 56%)',
  },
])
</script>
<template>
  <h1 class="overview-dashboard-header">Overview - Today</h1>
  <section class="overview-dashboard">
    <OverviewCard
      v-for="overviewDashboard in overviewDashboardData"
      :key="overviewDashboard.id"
      :title="overviewDashboard.title"
      :src="overviewDashboard.icon"
      :description="overviewDashboard.description"
      :followersAmount="overviewDashboard.followersAmount"
      :growthAmount="overviewDashboard.growthAmount"
      :growthIcon="overviewDashboard.growthIcon"
      :color="overviewDashboard.color"
    />
  </section>
</template>
<style lang="scss" scoped>
@import '../assets/sass/colors.scss';
@import '../assets/sass/fonts.scss';
.overview-dashboard-header {
  font-weight: changeFontWeight($bold-font-weight);
  color: changeFontColor($dark-grayish-blue);
  font-size: changeFontSize(1.75rem);
  padding: 1em 0.25em;
}
.overview-dashboard {
  padding: 0 0.25em;
  display: flex;
  flex-direction: column;
}
.overview-dashboard {
  display: flex;
  justify-content: center;
  align-items: center;
}
@media (min-width: 768px) {
  .overview-dashboard {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2em;
  }
}
@media (min-width: 1200px) {
  .overview-dashboard-header {
    padding: 1em 0;
  }
  .overview-dashboard {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
  }
}
</style>
