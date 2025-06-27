<script setup>
import HeaderDashboard from './HeaderDashboard.vue'
import ThemeDashboard from './ThemeDashboard.vue'
import ResultsDashboard from './ResultsDashboard.vue'
import OverviewDashboard from './OverviewDashboard.vue'
</script>
<template>
  <header class="dashboard-header-container wrapper">
    <HeaderDashboard />
    <ThemeDashboard />
  </header>
  <main class="results-dashboard-wide-layout wrapper">
    <ResultsDashboard />
    <OverviewDashboard />
  </main>
</template>
<style lang="scss" scoped>
@import '../assets/sass/colors.scss';
@import '../assets/sass/wrapper.scss';
.dashboard-header-container {
  padding-bottom: 1em;
}
.results-dashboard-wide-layout{
  display: flex;
  flex-direction: column;
}
@media (min-width: 768px) {
  .dashboard-header-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
}
</style>
