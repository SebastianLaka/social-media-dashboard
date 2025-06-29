<script setup>
import HeaderDashboard from './HeaderDashboard.vue'
import ThemeDashboard from './ThemeDashboard.vue'
import ResultsDashboard from './ResultsDashboard.vue'
import OverviewDashboard from './OverviewDashboard.vue'
import FooterDashboard from './FooterDashboard.vue'
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
  <footer>
    <FooterDashboard />
  </footer>
</template>
<style lang="scss">
@import '../assets/sass/colors.scss';
@import '../assets/sass/wrapper.scss';
@import '../assets/sass/mixins.scss';
body {
  padding: 2em 0;
}
html.dark {
  background-color: changeBackgroundColor($very-dark-blue-top-bg);
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
  .overview-dashboard-header {
    color: changeFontColor($dark-white);
  }
  .overview-dashboard-card {
    background-color: changeBackgroundColor($dark-desaturated-blue);
    &__title {
      color: changeFontColor($dark-desaturated-blue-text);
    }
    &__amount {
      color: changeFontColor($dark-white);
    }
  }

  .dashboard-card:hover,
  .overview-dashboard-card:hover {
    background-color: changeBackgroundColor($dark-grayish-blue);
  }
  .footer {
    &__description {
      color: changeFontColor($dark-grayish-blue);
      &--name {
        color: changeFontColor($dark-white);
      }
    }
  }
}
.dashboard-header-container {
  padding-bottom: 1em;
}
.results-dashboard-wide-layout {
  @include flex-column;
}
@media (min-width: 768px) {
  .dashboard-header-container {
    @include flex-align-center;
    justify-content: space-between;
  }
}
</style>
