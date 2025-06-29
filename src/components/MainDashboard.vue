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
<style lang="scss">
@import '../assets/sass/colors.scss';
@import '../assets/sass/wrapper.scss';

html.dark {
  background-color: $very-dark-blue;
  .dashboard-header {
    &__name {
      color: $dark-white;
    }
    &__amount-followers {
      color: $dark-desaturated-blue-text;
    }
  }
  .theme-area {
    &__header {
      color: $dark-white;
    }
    .theme-switch {
      &__button {
        color: $dark-desaturated-blue-text;
      }
    }
  }
  .dashboard-card {
    background-color: $dark-desaturated-blue;
    .dashboard-name {
      &__person-name {
        color: $dark-desaturated-blue-text;
      }
    }
    .dashboard-followers {
      &__amount {
        color: $dark-white;
      }
    }
  }
  .overview-dashboard-header{
    color: $dark-white;
  }
  .overview-dashboard-card {
    background-color: $dark-desaturated-blue;
    &__title {
      color: $dark-desaturated-blue-text;
    }
    &__amount{
      color: $dark-white;
    }
  }
}

.dashboard-header-container {
  padding-bottom: 1em;
}
.results-dashboard-wide-layout {
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
