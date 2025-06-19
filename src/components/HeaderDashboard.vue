<script setup>
import { ref } from 'vue';
const followersAmount = ref(23.004);
</script>
<template>
    <header class="dashboard-header">
        <h1 class="dashboard-header__name">Social Media Dashboard</h1>
        <p class="dashboard-header__amount-followers"> Total Followers: {{followersAmount}}</p>
    </header>
    
</template>
<style scoped lang="scss">
@import "../assets/sass/colors.scss";
@import "../assets/sass/fonts.scss";
.dashboard-header{
    border-bottom: 0.1em solid $dark-grayish-blue;
    padding: .25em .25em 1.25em .25em;
    &__name{
        font-size: 1.75rem;
    }
    &__amount-followers{
        font-size: $primary-font-size;
        font-weight: $bold-font-weight;
        color: $dark-grayish-blue;
    }
}
</style>