<script setup>
import ThemeButton from './ThemeButton.vue';

import { useDark } from '@vueuse/core'

const isDark = useDark({ disableTransition: false });

</script>

<template>
  <div class="theme-area">
    <h1 class="theme-area__header">Dark mode</h1>
    <ThemeButton v-model:isToggle="isDark" :isDark="isDark" />
  </div>
</template>

<style lang="scss" scoped>
@import '../assets/sass/colors.scss';
.theme-area {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1em 0.25em;
  &__header {
    color: $dark-grayish-blue;
  }
}
@media (min-width: 768px){
  .theme-area{
    &__header{
      padding: 0 1em 0 0;
    }
  }
}
</style>
