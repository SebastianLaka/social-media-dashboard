<template>
  <footer class="footer">
    <p class="footer__description">
      Challenge by Frontend Mentor. Coded by
      <span class="footer__description--name">SebastianLaka</span>
    </p>
  </footer>
</template>
<style lang="scss" scoped>
@import '../assets/sass/colors.scss';
@import '../assets/sass/fonts.scss';
@import '../assets/sass/mixins.scss';
.footer {
  @include flex-align-center;
  justify-content: center;
  padding-top: .75em;
  width: 100%;
  &__description {
    color: changeFontColor($dark-grayish-blue);
    padding: 1em;
    &--name {
      color: changeFontColor($very-dark-blue);
    }
  }
}
</style>
