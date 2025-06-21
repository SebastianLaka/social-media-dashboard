<script setup>
defineProps({
    isToggle: {type: Boolean, default: false} 
})
const emit = defineEmits(['update:isToggle']);
const handleChange = (event) => {
  emit('update:isToggle', event.target.checked);
};

</script>
<template>
    <label class="theme-switch" >
      <input class="theme-switch__button" type="checkbox" :checked="isToggle" @change="handleChange"/>
      <span class="switch round"></span>
    </label>
</template>
<style lang="scss" scoped>
@import "../assets/sass/colors.scss";
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
</style>