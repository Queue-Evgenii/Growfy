<template>
  <div class="page__services services-page">
    <div class="services-page__container _container">
      <div class="services-page__columns flex">
        <div class="services-page__column services-page__content content-block">
          <span class="before-title">services</span>
          <h2 class="services-page__title content-block__title">Services we offer.</h2>
          <p class="services-page__text content-block__text">Lorem ipsum dolor sit amet, consectetur adipiscing elit, suspendisse varius enim in eros elementum tristique. Duis cursus, mi quis viverra ornare, eros dolor.</p>
          <div class="services-page__button button content-block__button">
            <router-link to="" class="services-page__link">All services</router-link>
          </div>
        </div>
        <div class="services-page__column services-page__map map-services flex">
          <div class="map-services__column" v-for="column in this.MapContent" :key="column.id">
            <div class="map-services__item block-hover" v-for="item in column.items" :key="item.id">
              <div class="map-services__icon-row">
                <div class="map-services__icon"><img :src="item.icon" alt=""></div>
              </div>
              <h3 class="map-services__title">{{ item.title }}</h3>
              <p class="map-services__text">{{ item.text }}</p>
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
      MapContent: [
        {
          items: [
            {
              icon: require('@/assets/img/content/media.png'),
              title: 'Social Media Marketing',
              text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit lobortis arcu enim urna adipiscing praesent velit.'
            },
            {
              icon: require('@/assets/img/content/email.png'),
              title: 'Email Marketing',
              text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit lobortis arcu enim urna adipiscing praesent velit.'
            }
          ]
        },
        {
          items: [
            {
              icon: require('@/assets/img/content/paid.png'),
              title: 'Paid Advertising',
              text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit lobortis arcu enim urna adipiscing praesent velit.'
            },
            {
              icon: require('@/assets/img/content/seo.png'),
              title: 'SEO Optimization',
              text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit lobortis arcu enim urna adipiscing praesent velit.'
            }
          ]
        }
      ]
    }
  }
}
</script>
<style lang="scss">
.services-page {
  &__columns {
    justify-content: space-between;
    flex-wrap: wrap;
    row-gap: 32px;
  }
  &__column {
    flex: 0 0 50%;
  }
  &__content {
    flex: 0 0 512px;
    @media(max-width: 1220px) {
      flex: 0 1 70%;
    }
    @media(max-width: 768px) {
      flex: 0 1 100%;
    }
  }
  &__map {
    flex: 0 0 50%;
    @media(max-width: 1220px){
      flex: 1 1 100%;
    }
  }
}
.map-services {
  gap: 32px;
  @media(max-width: 768px){
    flex-direction: column;
  }
  &__column {
    display: flex;
    flex-direction: column;
    row-gap: 32px;
    min-width: 304px;
    &:nth-child(odd){
      margin-top: 48px;
    }
    @media(max-width: 1220px){
      &:nth-child(odd){
        margin-top: 0;
      }
    }
    @media(max-width: 400px) {
      min-width: initial;
    }
  }
  &__item {
    padding: 55px 25px;
    background-color: rgba(129, 129, 139, 0.1);
    border-radius: 30px;
    display: flex;
    flex-direction: column;
    row-gap: 10px;
  }
  &__icon-row {
    margin-bottom: 5px;
  }
  &__title {
    font-weight: 400;
    font-size: 19.2px;
    line-height: 27px;
    color: #FFFFFF;
  }
  &__text {
    font-size: 16px;
    line-height: 24px;
    color: #81818B;
  }
}
</style>
