<template>
  <div class="case-mini" :class="classes" v-on="$listeners">
    <img :src="image" width="84" height="84" loading="lazy" alt="product" />
  </div>
</template>

<script>
export default {
  props: {
    image: {
      type: String,
      required: true,
    },
    active: {
      type: Boolean,
      default: false,
    },
  },
  computed: {
    classes() {
      return {
        'case-mini--active': this.active,
      }
    },
  },
}
</script>

<style lang="sass" scoped>
.case-mini
  cursor: pointer
  -webkit-tap-highlight-color: transparent

  &--active
    position: relative
    &:before
      content: ""
      position: absolute
      border: 4px solid #FF840C
      top: -4px
      left: -4px
      right: 7px
      border-radius: 14px
      bottom: -4px
      @media (min-width: map-get($breakpoints, 'sm'))
        border: 3px solid #FF840C
        top: -1px
        left: -3px
        right: -3px
        border-radius: 10px
        bottom: -2px
      @media (min-width: map-get($breakpoints, 'lg'))
        border: 3px solid #FF840C
        border-radius: 12px
      @media (min-width: map-get($breakpoints, 'xxxl'))
        border: 4px solid #FF840C
        border-radius: 14px

  ::v-deep
    img
      border-radius: 10px
      height: auto
      display: block
      width: 64px
      @media (min-width: map-get($breakpoints, 'sm'))
        width: 45px
        border-radius: 10px
      @media (min-width: map-get($breakpoints, 'lg'))
        width: 64px
        border-radius: 12px
      @media (min-width: map-get($breakpoints, 'xxxl'))
        width: 84px
        border-radius: 14px
</style>
