<template>
  <section class="build-section">
    <ui-wrapper>
      <div class="build-section__inner">
        <h2 class="build-section__title title-secondary">
          Строим совместный бизнес
        </h2>
        <div class="build-section__title-info">
          Отвечаем на важные вопросы: почему делимся идеями товаров и кому
          подходит бизнес.
        </div>
        <div class="build-section__scroll">
          <ul ref="list" class="build-section__scroll-list">
            <li class="build-section__scroll-item">
              <app-advantage img="advantage-1.jpg">
                <template #icon>
                  <ui-icon name="icon-handshake"></ui-icon>
                </template>
                <template #title>
                  Мы делимся авторскими наработками, потому что франшиза
                  PriChina —
                </template>
                <template #description>
                  это сочетание товарной инфраструктуры (подбор, логистика,
                  хранение и упаковка) и предпринимателей, которые зарабатывают
                  от инвестиций в подобранными товары.
                </template>
              </app-advantage>
            </li>
            <li class="build-section__scroll-item">
              <app-advantage img="advantage-2.jpg" second>
                <template #icon>
                  <ui-icon name="icon-people"></ui-icon>
                </template>
                <template #title>
                  Сотрудничество будет привлекательным для:
                </template>
                <template #description>
                  <ul>
                    <li>Инвесторов, которые ищут пассивный доход.</li>
                    <li>
                      Предпринимателей или фрилансеров, которые ищут удаленную
                      формат бизнеса.
                    </li>
                    <li>
                      Любителей путешествовать и жить в курортных странах,
                      которые хотят создать активы для заработка.
                    </li>
                  </ul>
                </template>
              </app-advantage>
            </li>
          </ul>
        </div>
      </div>
      <div class="build-section__bottom-description">
        <h3>
          Подобный принцип работы применяют и сами маркетплейсы, которые
          предлагают услуги площадки взамен на комиссию с товара, вместо того,
          чтобы торговать на ней самостоятельно.
        </h3>
      </div>
    </ui-wrapper>
  </section>
</template>

<script>
export default {
  mounted() {
    const mm = this.$gsap.matchMedia()
    this.$nextTick(() => {
      mm.add('(min-width: 768px)', () => {
        this.$gsap.getById('invite-section').to(
          this.$refs.list,
          {
            x: () => -this.$refs.list?.firstChild?.offsetWidth,
          },
          -0.5
        )
      })
    })
  },
}
</script>

<style lang="sass" scoped>
.build-section
  color: #212121
  background-color: #f4f4f4
  border-radius: 0px 0px 60px 60px
  font-family: 'Manrope-Light'
  position: relative
  z-index: 4
  overflow: hidden
  @media (min-width: map-get($breakpoints, 'lg'))
    border-radius: 0px 0px 80px 80px

  &__inner
    padding: 81px 0 0 0
    @media (min-width: map-get($breakpoints, 'sm'))
      padding: 56px 0 0 0
    @media (min-width: map-get($breakpoints, 'lg'))
      padding: 70px 0 0 0

  &__title
    margin-bottom: 14px
    text-align: center
    @media (min-width: map-get($breakpoints, 'lg'))
      margin-bottom: 21px

  &__title-info
    text-align: center
    color: #A0A0A0
    font-size: 16px
    line-height: 24px
    max-width: 250px
    margin: 0 auto
    margin-bottom: 40px
    @media (min-width: map-get($breakpoints, 'sm'))
      max-width: 100%
      margin: 0
      margin-bottom: 52px
    @media (min-width: map-get($breakpoints, 'lg'))
      font-size: 18px
      line-height: 28px
    @media (min-width: map-get($breakpoints, 'xxxl'))
      font-size: 22px
      line-height: 33px

  &__scroll
    @media (min-width: map-get($breakpoints, 'sm'))
      padding-bottom: 60px
    @media (min-width: map-get($breakpoints, 'lg'))
      padding-bottom: 70px
    @media (min-width: map-get($breakpoints, 'xxxl'))
      padding-bottom: 90px

  &__scroll-list
    @media (min-width: map-get($breakpoints, 'sm'))
      display: flex
      flex-wrap: nowrap

  &__scroll-item
    margin-bottom: 50px
    @media (min-width: map-get($breakpoints, 'sm'))
      width: 100%
      padding-right: 37px
      margin-bottom: 0
    @media (min-width: map-get($breakpoints, 'lg'))
      padding-right: 96px
    @media (min-width: map-get($breakpoints, 'xxxl'))
      padding-right: 160px
      &::last-child
        padding-right: 0

  &__bottom-description
    margin: 0 auto
    text-align: center
    max-width: 582px
    padding: 0 0 60px 0
    @media (min-width: map-get($breakpoints, 'lg'))
      padding: 0 0 90px 0
      max-width: 646px
      @media (max-height: 800px)
        max-width: 850px
    @media (min-width: map-get($breakpoints, 'xxxl'))
      max-width: 978px
      @media (max-height: 800px)
        max-width: 850px
    h3
      font-family: 'Manrope-Light'
      font-weight: 300
      font-size: 18px
      line-height: 26px
      @media (min-width: map-get($breakpoints, 'lg'))
        font-size: 20px
        line-height: 30px
        @media (max-height: 800px)
          font-size: 26px
          line-height: 34px
      @media (min-width: map-get($breakpoints, 'xxxl'))
        font-size: 30px
        line-height: 45px
        @media (max-height: 800px)
          font-size: 26px
          line-height: 34px
</style>
