<script setup>
import { ref } from 'vue'
const followersAmount = ref(23.004)
</script>
<template>
  <div class="dashboard-header">
    <h1 class="dashboard-header__name">Social Media Dashboard</h1>
    <p class="dashboard-header__amount-followers">Total Followers: {{ followersAmount }}</p>
  </div>
</template>
<style scoped lang="scss">
@import '../assets/sass/colors.scss';
@import '../assets/sass/fonts.scss';
.dashboard-header {
  border-bottom: 0.1em solid $dark-grayish-blue;
  padding: 0.25em 0.25em 1.25em 0.25em;
  &__name {
    font-size: 1.75rem;
  }
  &__amount-followers {
    font-size: changeFontSize($primary-font-size);
    font-weight: changeFontWeight($bold-font-weight);
    color: changeFontColor($dark-grayish-blue);
  }
}
@media (min-width: 768px) {
  .dashboard-header {
    border-bottom: none;
  }
}
</style>
