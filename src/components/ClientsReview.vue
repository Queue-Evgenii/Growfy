<template>
  <div class="page__review review-page">
    <div class="review-page__container _container">
      <div class="review-page__rows">
        <div class="review-page__row row-content__flexbox">
          <div class="review-page__text-block content-block row-content__text-block">
            <span class="before-title">testimonials</span>
            <h2 class="review-page__title content-block__title row-content__title">See what our clients say</h2>
            <p class="review-page__text content-block__text row-content__text">Lorem ipsum dolor sit amet, consectetur adipiscing elit, suspendisse varius enim in eros elementum tristique. Duis cursus, mi quis viverra ornare, eros dolor.</p>
          </div>
          <div class="review-page__button-block row-content__button-block">
            <div class="review-page__button button content-block__button row-content__button">
              <router-link to="" class="review-page__link">Get in touch</router-link>
            </div>
          </div>
        </div>
        <div class="review-page__row">
          <div class="review-page__columns grid-columns">
            <div class="review-page__column grid-column block-hover" v-for="item in this.ReviewItems" :key="item.id">
              <div class="review-page__user flex">
                <div class="review-page__image"><img :src="item.logo" alt=""></div>
                <div class="review-page__info">
                  <div class="review-page__name">{{ item.name }}</div>
                  <div class="review-page__company">{{  item.company }}</div>
                </div>
              </div>
              <div class="review-page__review-content">
                <div class="review-page__review-title">{{ item.title }}</div>
                <div class="review-page__review-text">{{ item.text }}</div>
              </div>
              <div class="review-page__grade rating-page">
                <div class="rating-page__body"><div class="rating-page__active" v-bind:style="{width: 20*item.grade+'%'}"></div></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      ReviewItems: [
        {
          logo: require('@/assets/img/content/john-review.png'),
          name: 'John Doe',
          company: 'Company Name',
          title: '"I recommend this agency"',
          text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse varius dolor sit amet enim in eros elementum tristique. Duis dolor sit ametcursus, mi quisd dolor sit amet viverra ornare, eros dolor interdum nulla, ut commodo diam libero. Suspendisse varius dolor sit amet enim in eros elementum tristique.',
          grade: 5
        },
        {
          logo: require('@/assets/img/content/alice-review.png'),
          name: 'Alice Smith',
          company: 'Company Name',
          title: '"The support is awesome"',
          text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse varius enim in eros elementum tristique. Duis cursus, mi quis viverra ornare, eros dolor interdum nulla, ut commodo diam libero.',
          grade: 4
        },
        {
          logo: require('@/assets/img/content/sophia-review.png'),
          name: 'Sophia Miller',
          company: 'Company Name',
          title: '“A game changer for us”',
          text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse varius enim in eros elementum tristique. Duis cursus, mi quis viverra ornare, eros dolor interdum nulla, ut commodo diam libero.',
          grade: 5
        }
      ]
    }
  }
}
</script>
<style lang="scss">
.review-page {
  &__rows {
    display: flex;
    flex-direction: column;
    row-gap: 64px;
  }
  &__row {
  }
  &__link {
  }
  &__columns {
  }
  &__column {
    padding: 65px 40px;
    row-gap: 32px;
    @media(max-width: 430px) {
      padding: 50px 30px;
    }
  }
  &__user {
    gap: 16px;
    flex: 0 0 auto;
  }
  &__image {
    flex: 0 0 68px;
    width: 68px;
    height: 68px;
    position: relative;
    img {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
    }
    @media(max-width: 430px) {
      flex: 0 0 45px;
      width: 45px;
      height: 45px;
    }
  }
  &__info {
  }
  &__name {
    color: #FFFFFF;
  }
  &__company {
  }
  &__review-content{
    display: flex;
    flex-direction: column;
    row-gap: 25px;
    flex: 1 1 100%;
  }
  &__review-title {
    font-weight: 400;
    font-size: 32px;
    line-height: 45px;
    color: #FFFFFF;
    @media(max-width: 430px) {
      font-size: 25px;
      line-height: 30px;
    }
  }
  &__review-text {
  }
  &__grade {
  }
}
.rating-page{
  font-size: 24px;
  line-height: 0;
  display: flex;
  align-items: flex-end;
  letter-spacing: 5px;
  line-height: 0.75;
  &__body{
    position: relative;
    height: 20px;
    width: 120px;
    &::before{
      content: '★★★★★';
      position: absolute;
      display: block;
    }
  }
  &__active{
    position: absolute;
    height: 100%;
    left: 0;
    top: 0;
    overflow: hidden;
    &::before{
      content: '★★★★★';
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      color: #FFC54F;
    }
  }
}
</style>
