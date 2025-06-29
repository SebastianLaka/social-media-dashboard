<script setup>
import { computed } from 'vue'
const props = defineProps({
  name: String,
  src: {
    type: String,
    required: true,
  },
  alt: String,
  followersAmount: {
    type: Number,
    default: 0,
  },
  followers: String,
  amount: Number,
  borderColor: {
    type: String,
    default: 'transparent',
  },
  growthIcon: {
    type: String,
    required: false,
  },
  color: {
    type: String,
    default: 'transparent',
  },
})

const convertAtKValues = computed(() => {
  if (props.followersAmount > 10000) {
    return (props.followersAmount / 1000).toFixed(0) + 'k'
  } else {
    return props.followersAmount
  }
})
</script>
<template>
  <div class="dashboard-card">
    <div class="dashboard-card__top-border" :style="{ background: props.borderColor }"></div>
    <div class="dashboard-name">
      <img :src="props.src" :alt="props.alt" class="dashboard-name__icon" />
      <p class="dashboard-name__person-name">{{ props.name }}</p>
    </div>
    <div class="dashboard-followers">
      <p class="dashboard-followers__amount">{{ convertAtKValues }}</p>
      <p class="dashboard-followers__followers">{{ props.followers }}</p>
    </div>
    <div class="dashboard-followers-growth">
      <img :src="props.growthIcon" :alt="props.alt" class="dashboard-followers-growth__icon" />
      <p class="dashboard-followers-growth__amount" :style="{ color: props.color }">
        {{ props.amount }}
      </p>
      <p class="dashboard-followers-growth__current-day" :style="{ color: props.color }">Today</p>
    </div>
  </div>
</template>
<style lang="scss" scoped>
@import '../assets/sass/colors.scss';
@import '../assets/sass/fonts.scss';
@import "../assets/sass/mixins.scss";
.dashboard-card {
  position: relative;
  border-radius: 0.2em;
  @include flex-align-center;
  flex-direction: column;
  gap: 1em 0;
  padding: 2em 0;
  cursor: pointer;
  transition: background-color 0.3s ease-in-out;
  &__top-border {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 0.25em;
    border-top-left-radius: 0.2em;
    border-top-right-radius: 0.2em;
  }
  .dashboard-name,
  .dashboard-followers-growth {
    @include flex-align-center;
    gap: 0 0.2em;
    &__person-name {
      font-weight: changeFontWeight($bold-font-weight);
    }
    &__amount,
    &__current-day {
      color: changeFontColor($primary-lime-green);
      font-weight: changeFontWeight($bold-font-weight);
    }
  }
  .dashboard-followers {
    @include flex-align-center;
    flex-direction: column;
    &__amount {
      font-size: changeFontSize(3.5rem);
      font-weight: changeFontWeight($bold-font-weight);
    }
    &__followers {
      letter-spacing: 0.2em;
      color: changeFontColor($dark-grayish-blue);
      font-size: changeFontSize($primary-font-size);
    }
  }
}
.dashboard-card:hover {
  background-color: changeBackgroundColor($toggle-light-theme);;
}
@media (min-width: 0px) and (max-width: 768px) {
  .dashboard-card {
    width: 85%;
  }
}
</style>
