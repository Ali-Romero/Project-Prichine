<template>
  <div class="circle-slider" :class="classes">
    <div class="circle-slider__slide circle-slider__slide--1">
      <div class="circle-slider__item">
        <ui-icon name="diff-search" class="circle-slider__icon" />
      </div>
    </div>
    <div class="circle-slider__slide circle-slider__slide--2">
      <div class="circle-slider__item">
        <ui-icon name="diff-box" class="circle-slider__icon" />
      </div>
    </div>
    <div class="circle-slider__slide circle-slider__slide--3">
      <div class="circle-slider__item">
        <ui-icon name="diff-calc" class="circle-slider__icon" />
      </div>
    </div>
    <div class="circle-slider__slide circle-slider__slide--4">
      <div class="circle-slider__item">
        <ui-icon name="diff-voice" class="circle-slider__icon" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    slide: {
      type: Number,
      default: 1,
    },
  },
  computed: {
    classes() {
      return [`circle-slider--current-${this.slide}`]
    },
  },
}
</script>

<style lang="sass" scoped>
.circle-slider
  position: relative
  width: 500px
  height: 500px
  border: 2px solid #FFFFFF
  border-radius: 100%
  transition: transform 0.2s
  margin: 0 auto
  @media (min-width: map-get($breakpoints, 'md'))
    border: 3px solid #FFFFFF
    margin: 0
    width: 510px
    height: 510px
  @media (min-width: map-get($breakpoints, 'lg'))
    width: 600px
    height: 600px
  @media (min-width: map-get($breakpoints, 'xxxl'))
    width: 893px
    height: 893px
    @media (max-height: 800px)
      width: 700px
      height: 700px

  &::before
    @media (min-width: map-get($breakpoints, 'md'))
      content: ''
      width: 340px
      height: 340px
      margin: auto
      position: absolute
      top: 0
      left: 0
      bottom: 0
      right: 0
      border: 3px solid #FFFFFF
      opacity: 0.5
      border-radius: 100%
    @media (min-width: map-get($breakpoints, 'lg'))
      width: 430px
      height: 430px
    @media (min-width: map-get($breakpoints, 'xxxl'))
      width: 621px
      height: 621px
      @media (max-height: 800px)
        width: 560px
        height: 560px

  &--current-2
    transform: rotate(-20deg)
    @media (min-width: map-get($breakpoints, 'md'))
      transform: rotate(-35deg)

  &--current-3
    transform: rotate(-40deg)
    @media (min-width: map-get($breakpoints, 'md'))
      transform: rotate(-70deg)

  &--current-4
    transform: rotate(-60deg)
    @media (min-width: map-get($breakpoints, 'md'))
      transform: rotate(-105deg)

  &--current-1 &__slide--1 &__item &__icon
    transform: scale(1)
    @media (min-width: map-get($breakpoints, 'md'))
      transform: scale(1) rotate(270deg)

  &--current-1 &__slide--1 &__item
    width: 56px
    height: 56px
    background: #1776D4
    box-shadow: 0px 8px 11px rgba(23, 60, 98, 0.21)
    @media (min-width: map-get($breakpoints, 'md'))
      box-shadow: 0px 25px 29px rgba(23, 60, 98, 0.21)
      width: 70px
      height: 70px
    @media (min-width: map-get($breakpoints, 'xxxl'))
      width: 86px
      height: 86px

  &--current-2 &__slide--2 &__item &__icon
    transform: scale(1)
    @media (min-width: map-get($breakpoints, 'md'))
      transform: scale(1) rotate(270deg)

  &--current-2 &__slide--2 &__item
    width: 56px
    height: 56px
    background: #1776D4
    box-shadow: 0px 8px 11px rgba(23, 60, 98, 0.21)
    @media (min-width: map-get($breakpoints, 'md'))
      box-shadow: 0px 25px 29px rgba(23, 60, 98, 0.21)
      width: 70px
      height: 70px
    @media (min-width: map-get($breakpoints, 'xxxl'))
      width: 86px
      height: 86px

  &--current-3 &__slide--3 &__item &__icon
    transform: scale(1)
    @media (min-width: map-get($breakpoints, 'md'))
      transform: scale(1) rotate(270deg)

  &--current-3 &__slide--3 &__item
    width: 56px
    height: 56px
    background: #1776D4
    box-shadow: 0px 8px 11px rgba(23, 60, 98, 0.21)
    @media (min-width: map-get($breakpoints, 'md'))
      box-shadow: 0px 25px 29px rgba(23, 60, 98, 0.21)
      width: 70px
      height: 70px
    @media (min-width: map-get($breakpoints, 'xxxl'))
      width: 86px
      height: 86px

  &--current-4 &__slide--4 &__item &__icon
    transform: scale(1)
    @media (min-width: map-get($breakpoints, 'md'))
      transform: scale(1) rotate(270deg)

  &--current-4 &__slide--4 &__item
    width: 56px
    height: 56px
    background: #1776D4
    box-shadow: 0px 8px 11px rgba(23, 60, 98, 0.21)
    @media (min-width: map-get($breakpoints, 'md'))
      box-shadow: 0px 25px 29px rgba(23, 60, 98, 0.21)
      width: 70px
      height: 70px
    @media (min-width: map-get($breakpoints, 'xxxl'))
      width: 86px
      height: 86px

  &__slide
    width: 100%
    height: 100%
    position: absolute
    top: 0
    right: 0

    &--1
      transform: rotate(0deg)
      @media (min-width: map-get($breakpoints, 'md'))
        transform: rotate(90deg)

    &--2
      transform: rotate(20deg)
      @media (min-width: map-get($breakpoints, 'md'))
        transform: rotate(125deg)

    &--3
      transform: rotate(40deg)
      @media (min-width: map-get($breakpoints, 'md'))
        transform: rotate(160deg)

    &--4
      transform: rotate(60deg)
      @media (min-width: map-get($breakpoints, 'md'))
        transform: rotate(195deg)

  &__item
    display: flex
    align-items: center
    justify-content: center
    width: 10px
    height: 10px
    margin: auto
    position: absolute
    top: 0
    right: 0
    left: 0
    transform: translateY(-50%)
    border-radius: 100%
    background: #212121
    transition: all 0.2s
    @media (min-width: map-get($breakpoints, 'md'))
      width: 16px
      height: 16px
    @media (min-width: map-get($breakpoints, 'lg'))
      width: 18px
      height: 18px
    @media (min-width: map-get($breakpoints, 'xxxl'))
      width: 20px
      height: 20px

  &__icon
    transform: scale(0)
    transition: transform 0.2s
    width: 40px
    height: 40px
    @media (min-width: map-get($breakpoints, 'md'))
      width: 41px
      height: 44px
    @media (min-width: map-get($breakpoints, 'xxxl'))
      width: 45px
      height: 48px
</style>
