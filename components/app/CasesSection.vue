<template>
  <section id="cases-section" class="cases-section">
    <div ref="nav" class="cases-section__nav d-none d-sm-block">
      <app-header></app-header>
    </div>
    <ui-wrapper>
      <div class="cases-section__inner">
        <h2 ref="titleAnim" class="cases-section__title title-secondary">
          Реальные кейсы
        </h2>
        <div ref="titleTextAnim" class="cases-section__title-info info">
          Для всех партнёров проводится постоянный мониторинг спроса товаров на
          маркетплейсах, на основе которого готовится подборка перспективных
          позиций на продажу.
        </div>
        <div class="cases-section__content">
          <div ref="productMiniAnim" class="cases-section__mini">
            <div class="product-mini">
              <div class="product-mini__image">
                <ui-image
                  src="multi-logo.png"
                  alt="image"
                  width="150"
                  height="56"
                  sizes="xxs:108 sm:120 lg:114 xxxl:150px"
                ></ui-image>
              </div>
              <div class="product-mini__title">
                На чём сегодня зарабатывают партнёры PriChina
              </div>
              <div class="product-mini__mobile d-sm-none">
                <app-cases-swiper
                  :products="products"
                  :active="slide"
                  @select="select"
                />
              </div>
              <div class="d-none d-sm-block">
                <div class="product-mini__cases-list">
                  <div
                    v-for="product in products"
                    :key="product.id"
                    class="product-mini__cases-item"
                  >
                    <app-case-mini
                      :image="product.thumbnail"
                      :active="product.id === slide"
                      @click="slide = product.id"
                    />
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div ref="productAnim" class="cases-section__product">
            <div v-show="false">
              <ui-image
                v-for="product in products"
                :key="product.id"
                :src="product.image"
                alt="image"
                width="452"
                height="550"
                sizes="xxs:280px lg:267px xxxl:452px"
              />
            </div>
            <transition name="fade" mode="out-in">
              <app-product-card
                :key="slide"
                :title="currentProduct.title"
                :image="currentProduct.image"
                :amount="currentProduct.amount"
                :profit="currentProduct.profit"
                :price-purchase="currentProduct.pricePurchase"
                :price-sale="currentProduct.priceSale"
                :markup="currentProduct.markup"
              />
            </transition>
            <div class="cases-section__nav-button">
              <div class="cases-section__nav-button-prev swiper-button-prev">
                <ui-nav-button prev @click="prev"></ui-nav-button>
              </div>
              <div class="cases-section__nav-button-next swiper-button-next">
                <ui-nav-button next @click="next"></ui-nav-button>
              </div>
            </div>
          </div>
        </div>
        <div class="cases-section__bottom-info">
          <div class="cases-section__bottom-img">
            <ui-image
              src="cases-bottom-img.jpg"
              alt="image"
              width="652"
              height="312"
              sizes="xxs:326px lg:490 xxxl:652px"
            ></ui-image>
          </div>
          <div class="cases-section__bottom-text">
            <h3>
              Каждый партнёр получил на старте вводное обучение и список ходовых
              товаров на выбор, и за месяц вышел на продажи.
            </h3>
          </div>
        </div>
      </div>
    </ui-wrapper>
  </section>
</template>

<script>
export default {
  data() {
    return {
      slide: 1,
      products: [
        {
          id: 1,
          thumbnail: require('@/assets/images/product-mini-1.jpg'),
          title: 'Плащ дождевик для крупных и средних собак',
          image: 'product-main-1.jpg',
          amount: '544 за месяц',
          profit: '451 106 рублей',
          pricePurchase: '356 рублей',
          priceSale: '1 084 рублей',
          markup: '254%',
        },
        {
          id: 2,
          thumbnail: require('@/assets/images/product-mini-2.jpg'),
          title: 'Набор дозаторов для ванной',
          image: 'product-main-2.jpg',
          amount: '1 559 за месяц',
          profit: '1 948 961 рублей',
          pricePurchase: '430 рублей',
          priceSale: '1 059 рублей',
          markup: '246%',
        },
        {
          id: 3,
          thumbnail: require('@/assets/images/product-mini-3.jpg'),
          title: 'Подшлемник балаклава',
          image: 'product-main-3.jpg',
          amount: '1 054 за месяц',
          profit: '498 634 рублей',
          pricePurchase: '80 рублей',
          priceSale: '406 рублей',
          markup: '507%',
        },
        {
          id: 4,
          thumbnail: require('@/assets/images/product-mini-4.jpg'),
          title: 'Пакеты фасовочные для вакууматора',
          image: 'product-main-4.jpg',
          amount: '1 133 за месяц',
          profit: '1 272 425 рублей',
          pricePurchase: '307 рублей',
          priceSale: '968 рублей',
          markup: '315%',
        },
        {
          id: 5,
          thumbnail: require('@/assets/images/product-mini-5.jpg'),
          title: 'Органайзер для хранения одежды и вещей',
          image: 'product-main-5.jpg',
          amount: '380 за месяц',
          profit: '470 106 рублей',
          pricePurchase: '312 рублей',
          priceSale: '1 084 рублей',
          markup: '347%',
        },
        {
          id: 6,
          thumbnail: require('@/assets/images/product-mini-6.jpg'),
          title: 'Лежанка гамак для кошек',
          image: 'product-main-6.jpg',
          amount: '806 за месяц',
          profit: '661 100 рублей',
          pricePurchase: '249 рублей',
          priceSale: '779 рублей',
          markup: '312%',
        },
        {
          id: 7,
          thumbnail: require('@/assets/images/product-mini-7.jpg'),
          title: 'Жилет для собак',
          image: 'product-main-7.jpg',
          amount: '690 за месяц',
          profit: '453 784 рублей',
          pricePurchase: '119 рублей',
          priceSale: '714 рублей',
          markup: '600%',
        },
        {
          id: 8,
          thumbnail: require('@/assets/images/product-mini-8.jpg'),
          title: 'Рубашка медицинская женская',
          image: 'product-main-8.jpg',
          amount: '827 за месяц',
          profit: '1 572 331 рублей',
          pricePurchase: '489 рублей',
          priceSale: '1 752 рублей',
          markup: '358%',
        },
        {
          id: 9,
          thumbnail: require('@/assets/images/product-mini-9.jpg'),
          title: 'Спортивные женские шорты',
          image: 'product-main-9.jpg',
          amount: '3 560 за месяц',
          profit: '4 912 800 рублей',
          pricePurchase: '456 рублей',
          priceSale: '1 117 рублей',
          markup: '244%',
        },
        {
          id: 10,
          thumbnail: require('@/assets/images/product-mini-10.jpg'),
          title: 'Утягивающий корсет',
          image: 'product-main-10.jpg',
          amount: '3 155 за месяц',
          profit: '4 388 364 рублей',
          pricePurchase: '312 рублей',
          priceSale: '1 492 рублей',
          markup: '478%',
        },
      ],
    }
  },
  computed: {
    currentProduct() {
      return this.products[this.slide - 1]
    },
  },
  mounted() {
    const mm = this.$gsap.matchMedia()
    this.$nextTick(() => {
      mm.add('(min-width: 768px)', () => {
        const tl = this.$gsap.getById('cases-section')
        tl.to(
          this.$refs.nav,
          {
            opacity: 1,
            scale: 1,
            y: -20,
          },
          0.2
        )
        tl.fromTo(
          this.$refs.titleAnim,
          {
            opacity: 0,
            x: '100%',
            ease: 'power1.out',
          },
          {
            opacity: 1,
            x: 0,
            ease: 'power1.out',
          },
          0
        )
        tl.fromTo(
          this.$refs.titleTextAnim,
          {
            opacity: 0,
            y: '200%',
            scale: 0,
            ease: 'power1.out',
          },
          {
            scale: 1,
            opacity: 1,
            y: 0,
            ease: 'power1.out',
          },
          0
        )
        tl.fromTo(
          this.$refs.productMiniAnim,
          {
            opacity: 0,
            x: '-100%',
            ease: 'power1.out',
          },
          {
            opacity: 1,
            x: 0,
            ease: 'power1.out',
          },
          0
        )
        tl.fromTo(
          this.$refs.productAnim,
          {
            opacity: 0,
            x: '100%',
            ease: 'power1.out',
          },
          {
            opacity: 1,
            x: 0,
            ease: 'power1.out',
          },
          0
        )
      })
    })
  },
  methods: {
    next() {
      // this.slide = this.slide === this.products.length ? 1 : this.slide + 1
      this.slide = Math.min(this.slide + 1, this.products.length)
    },
    prev() {
      // this.slide = this.slide === 1 ? this.products.length : this.slide - 1
      this.slide = Math.max(this.slide - 1, 1)
    },
    select(id) {
      this.slide = id
    },
  },
}
</script>

<style lang="sass" scoped>
.cases-section
  color: #212121
  position: relative
  z-index: 2
  background-color: white

  &__nav
    transform: scale(0.98)
    transition: 0.1s
    position: relative
    top: 20px
    z-index: 22
    ::v-deep
      .header-nav__item
        &:nth-child(2)
          pointer-events: none
          color: #FF840C

  &__inner
    padding: 81px 0 0 0
    @media (min-width: map-get($breakpoints, 'sm'))
      padding: 20px 0 0 0

  &__title
    margin-bottom: 21px
    text-align: center

  &__title-info
    font-family: 'Manrope-Light'
    max-width: 704px
    margin: 0 auto 48px auto
    color: #7D7D7D
    @media (min-width: map-get($breakpoints, 'sm'))
    margin: 0 auto 70px auto
    @media (min-width: map-get($breakpoints, 'lg'))
      margin: 0 auto 48px auto
      max-width: 836px
    @media (min-width: map-get($breakpoints, 'xxxl'))
      max-width: 963px

  &__content
    margin-bottom: 48px
    @media (min-width: map-get($breakpoints, 'sm'))
      margin-bottom: 85px
      display: flex
      justify-content: space-between

  &__mini
    @media (min-width: map-get($breakpoints, 'sm'))
      width: 100%
      max-width: 243px
    @media (min-width: map-get($breakpoints, 'lg'))
      max-width: 348px
    @media (min-width: map-get($breakpoints, 'xxxl'))
      max-width: 444px

  &__product
    max-width: 486px
    width: 100%
    position: relative
    @media (min-width: map-get($breakpoints, 'lg'))
      max-width: 665px
    @media (min-width: map-get($breakpoints, 'xxxl'))
      max-width: 933px

  &__bottom-info
    display: flex
    align-items: center
    justify-content: space-between
    flex-direction: column-reverse
    @media (min-width: map-get($breakpoints, 'sm'))
      flex-direction: row

  &__bottom-img
    ::v-deep
      img
        width: 326px
        height: auto
        @media (min-width: map-get($breakpoints, 'lg'))
          width: 490px
        @media (min-width: map-get($breakpoints, 'xxxl'))
          width: 652px

  &__bottom-text
    @media (min-width: map-get($breakpoints, 'sm'))
      max-width: 402px
    @media (min-width: map-get($breakpoints, 'lg'))
      max-width: 520px
    @media (min-width: map-get($breakpoints, 'xxxl'))
      max-width: 657px
    h3
      font-family: 'Manrope-Light'
      font-size: 18px
      line-height: 24px
      font-weight: 300
      @media (min-width: map-get($breakpoints, 'sm'))
        font-size: 19px
        line-height: 26px
      @media (min-width: map-get($breakpoints, 'lg'))
        font-size: 24px
        line-height: 35px
      @media (min-width: map-get($breakpoints, 'xxxl'))
        font-size: 30px
        line-height: 45px

  &__nav-button
    display: flex
    justify-content: center
    @media (min-width: map-get($breakpoints, 'sm'))
      justify-content: flex-start
      position: absolute
      bottom: 0px
      left: 196px
    @media (min-width: map-get($breakpoints, 'lg'))
      bottom: 4px
      left: 298px
    @media (min-width: map-get($breakpoints, 'xxxl'))
      bottom: 45px
      left: 500px

  &__nav-button-prev
    margin-right: 10px

.product-mini
  font-size: 17px
  line-height: 26px
  font-family: 'Manrope-Light'
  text-align: center
  @media (min-width: map-get($breakpoints, 'sm'))
    text-align: left
  @media (min-width: map-get($breakpoints, 'lg'))
    font-size: 22px
    line-height: 30px
  @media (min-width: map-get($breakpoints, 'xxxl'))
    font-size: 30px
    line-height: 42px

  &__image
    margin-bottom: 7px
    @media (min-width: map-get($breakpoints, 'sm'))
      margin-bottom: 5px
    @media (min-width: map-get($breakpoints, 'lg'))
      margin-bottom: 16px
    @media (min-width: map-get($breakpoints, 'xxxl'))
      margin-bottom: 21px
    ::v-deep
      img
        width: 90px
        height: auto
        margin: 0 auto
        @media (min-width: map-get($breakpoints, 'sm'))
          margin: 0
        @media (min-width: map-get($breakpoints, 'lg'))
          width: 114px
        @media (min-width: map-get($breakpoints, 'xxxl'))
          width: 150px

  &__title
    margin-bottom: 29px
    @media (min-width: map-get($breakpoints, 'sm'))
      margin-bottom: 26px
    @media (min-width: map-get($breakpoints, 'lg'))
      margin-bottom: 34px
    @media (min-width: map-get($breakpoints, 'xxxl'))
      margin-bottom: 135px

  &__cases-list
    display: flex
    flex-wrap: wrap
    justify-content: space-between

  &__cases-item
    margin-bottom: 4px
    @media (min-width: map-get($breakpoints, 'lg'))
      margin-bottom: 6px

  &__mobile
    margin-bottom: 38px
</style>
