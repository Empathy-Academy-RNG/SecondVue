<template>
  <svg
    class="search-icon"
    fill="none"
    height="120"
    viewBox="0 0 24 24"
    width="120"
    xmlns="http://www.w3.org/2000/svg"
  >
    <transition mode="out-in" name="search-loading-">
      <g
        v-if="this.$store.state.currentlySearching"
        class="search-icon__spinner"
      >
        <circle
          class="search-icon__spinner-bubble bubble1"
          cx="7"
          cy="11"
          r="0.65"
        />
        <circle
          class="search-icon__spinner-bubble bubble2"
          cx="11"
          cy="11"
          r="0.65"
        />
        <circle
          class="search-icon__spinner-bubble bubble3"
          cx="15"
          cy="11"
          r="0.65"
        />
      </g>
    </transition>
  </svg>
</template>

<script>
export default {
  name: "Loading"
};
</script>

<style lang="scss" scoped>
.search-icon {
  stroke: black;
  stroke-linecap: round;
  stroke-linejoin: round;
  stroke-width: 1.4;
  margin-top: -40px;
  margin-bottom: 70px;
}

.bubble1 {
  animation: blinkingFirst 1s ease-in-out infinite;
}
.bubble2 {
  animation: blinkingSecond 1s ease-in-out infinite;
}
.bubble3 {
  animation: blinkingThird 1s ease-in-out infinite;
}

.search-icon {
  &__spinner {
    animation: blinking 1s ease-in-out infinite;
  }
}

@keyframes blinkingFirst {
  0% {
    opacity: 0;
  }

  50% {
    opacity: 0.9;
  }

  100% {
    opacity: 0;
  }
}

@keyframes blinkingSecond {
  0% {
    opacity: 0.4;
  }

  50% {
    opacity: 0.6;
  }

  100% {
    opacity: 0;
  }
}
@keyframes blinkingThird {
  0% {
    opacity: 0.9;
  }

  50% {
    opacity: 0.2;
  }

  100% {
    opacity: 0.9;
  }
}
</style>
