<template>
  <div class="page">
    <transition name="fade-blur">
      <div v-if="loading" class="page__overlay">
        <div class="page__spinner page__spinner--1" />
        <div class="page__spinner page__spinner--2" />
        <div class="page__spinner page__spinner--3" />
      </div>
    </transition>

    <slot />
  </div>
</template>

<script>
export default {
  data() {
    return {
      loading: true,
    }
  },
  mounted() {
    this.loading = false
  },
}
</script>

<style lang="sass" scoped>
.page
  height: 100%

  &__overlay
    display: flex
    align-items: center
    justify-content: center
    width: 100%
    height: 100%
    position: fixed
    z-index: 9999
    top: 0
    left: 0
    background-color: #F4F4F4

  &__spinner
    width: 10px
    height: 10px
    border-radius: 100%
    background-color: #FF840C
    animation: loading 0.4s infinite alternate-reverse

    &--2
      margin: 0 4px
      animation-delay: 0.1s

    &--3
      animation-delay: 0.2s

@keyframes loading
  from
    transform: scale(1)

  to
    transform: scale(0.5)
</style>
