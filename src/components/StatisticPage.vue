<template>
  <div class="page__statictic statistic-page">
    <div class="statistic-page__container _container">
      <div class="statistic-page__columns flex">
        <div class="statistic-page__column statistic-page__items">
          <div class="statistic-page__item block-hover" v-for="item in this.StatisticItems" :key="item.id">
            <h2 class="statistic-page__title content-block__title">{{ item.title }}</h2>
            <p class="statistic-page__text content-block__text">{{ item.text }}</p>
          </div>
        </div>
        <div class="statistic-page__column statistic-page__images">
          <div class="statistic-page__big-image"></div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      StatisticItems: [
        {
          title: '1.2M+',
          text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse varius enim.'
        },
        {
          title: '3.4B',
          text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse varius enim.'
        },
        {
          title: '98%',
          text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse varius enim.'
        },
        {
          title: '10+',
          text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse varius enim.'
        }
      ]
    }
  }
}
</script>
<style lang="scss">
.statistic-page {
  &__columns {
    column-gap: 32px;
  }
  &__column {
  }
  &__items{
    flex: 1 1 750px;
    display: grid;
    grid-template-columns: repeat(2, minmax(220px, 1fr));
    gap: 32px;
    @media(max-width: 670px){
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    }
  }
  &__item {
    padding: 40px;
    background: rgba(129, 129, 139, 0.1);
    border-radius: 30px;
  }
  &__title {
  }
  &__text {
  }
  &__images {
    @media(max-width: 992px) {
      display: none;
    }
  }
  &__big-image {
    height: 588px;
    width: 500px;
    background: url('@/assets/img/content/stat-big-orange.png') center / 100% no-repeat;
    @media(max-width: 1200px){
      width: 390px;
    }
  }
}
</style>
