<script setup>
import ThemeButton from "./themeButton.vue"
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
@import "../assets/sass/mixins.scss";
.theme-area {
  @include flex-align-center;
  justify-content: space-between;
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
