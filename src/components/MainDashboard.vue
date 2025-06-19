<script setup>
import HeaderDashboard from './HeaderDashboard.vue'
import ThemeDashboard from './ThemeDashboard.vue'
</script>
<template>
    <header class="dashboard-header-container wrapper">
      <HeaderDashboard />
      <ThemeDashboard />
    </header>
</template>
<style lang="scss" scoped>
@import '../assets/sass/colors.scss';
@import '../assets/sass/wrapper.scss';
@media (min-width: 768px) {
    .dashboard-header-container {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
}
</style>
