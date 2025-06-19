<script setup></script>
<template>
  <div class="theme-area">
    <h1 class="theme-area__header">Dark mode</h1>
    <label class="theme-switch">
      <input class="theme-switch__button" type="checkbox" />
      <span class="switch round"></span>
    </label>
  </div>
</template>
<style lang="scss" scoped>
@import '../assets/sass/colors.scss';
.theme-area {
  display: flex;
  justify-content: space-between;
  padding: 1em 0.25em;
  &__header {
    color: $dark-grayish-blue;
  }
  .theme-switch {
    position: relative;
    display: inline-block;
    width: 3.5em;
    height: 1.75em;
    &__button {
      opacity: 0;
      width: 0;
      height: 0;
    }
    .switch {
      position: absolute;
      cursor: pointer;
      inset: 0;
      border-radius: 0.8em;
      transition: 0.4s;
      background-color: $toggle-light-theme;
    }
    .switch::before {
      position: absolute;
      content: '';
      height: 1.25em;
      width: 1.25em;
      left: 4px;
      bottom: 4px;
      background-color: white;
      border-radius: 50%;
      transition: 0.4s;
    }
    input:checked + .switch {
      background: $toggle-dark-theme;
    }
    input:checked + .switch:before {
      -webkit-transform: translateX(26px);
      -ms-transform: translateX(26px);
      transform: translateX(26px);
      background-color: $very-dark-blue;
    }
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
