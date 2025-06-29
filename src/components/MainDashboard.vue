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
body{
  padding: 3em 0;
}

html.dark {
  background-color:changeBackgroundColor($very-dark-blue-top-bg);
  .dashboard-header {
    &__name {
      color: changeFontColor($dark-white);
    }
    &__amount-followers {
      color: changeFontColor($dark-desaturated-blue-text);
    }
  }
  .theme-area {
    &__header {
      color: changeFontColor($dark-white);
    }
    .theme-switch {
      &__button {
        color: changeFontColor($dark-desaturated-blue-text);
      }
    }
  }
  .dashboard-card {
    background-color: $dark-desaturated-blue;
    .dashboard-name {
      &__person-name {
        color: changeFontColor($dark-desaturated-blue-text);
      }
    }
    .dashboard-followers {
      &__amount {
        color: changeFontColor($dark-white);
      }
    }
  }
  .overview-dashboard-header{
    color: changeFontColor($dark-white);
  }
  .overview-dashboard-card {
    background-color: changeBackgroundColor($dark-desaturated-blue);
    &__title {
      color: changeFontColor($dark-desaturated-blue-text);
    }
    &__amount{
      color: changeFontColor($dark-white);
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
