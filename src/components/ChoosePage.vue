<template>
  <div class="page__choose choose-page">
    <div class="choose-page__container _container">
      <div class="choose-page__columns flex">
        <div class="choose-page__column choose-page__images">
          <div class="choose-page__big-image"></div>
          <div class="choose-page__small-image"></div>
          <img src="@/assets/img/content/decor.png" alt="" class="choose-page__decor decor">
        </div>
        <div class="choose-page__column content-block">
          <span class="before-title">why choose us</span>
          <h2 class="choose-page__title content-block__title">We help great brands scale with content marketing.</h2>
          <p class="choose-page__text content-block__text">Lorem ipsum dolor sit amet, consectetur adipiscing elit, suspendisse varius enim in eros elementum tristique. Duis cursus, mi quis viverra ornare, eros dolor.</p>
          <ul class="choose-page__items">
            <li class="choose-page__item flex" v-for="item in this.ChooseList" :key="item.id">{{item.text}}</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      ChooseList: [
        {
          text: 'This is some text inside of a div.'
        },
        {
          text: 'This is some text inside of a div.'
        },
        {
          text: 'This is some text inside of a div.'
        },
        {
          text: 'This is some text inside of a div.'
        }
      ]
    }
  }
}
</script>
<style lang="scss">
.choose-page {
  &__decor{
    bottom: 0;
    left: 0;
    @media(max-width: 992px) {
      bottom: 110px;
    }
  }
  &__columns {
    column-gap: 64px
  }
  &__images{
    position: relative;
    display: flex;
    align-items: end;
    @media(max-width: 768px) {
      display: none;
    }
  }
  &__small-image,
  &__big-image{
    position: relative;
    img{
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
    }
  }
  &__big-image {
    background: url('@/assets/img/content/choose-big-green.png') center / 100% no-repeat;
    height: 785px;
    width: 423px;
    @media(max-width: 1024px) {
      width: 300px;
    }
    @media(max-width: 992px) {
      width: 260px;
    }
  }
  &__small-image {
    background: url('@/assets/img/content/choose-small-orange.png') center / 100% no-repeat;
    height: 181px;
    width: 181px;
    @media(max-width: 1200px) {
      display: none;
    }
  }
  &__title,
  &__text {
    margin-bottom: 20px;
  }
  &__items {
  }
  &__item {
    position: relative;
    padding: 0 0 0 42px;
    &:not(:last-child) {
      margin-bottom: 20px;
    }
    &::after{
      content: '';
      position: absolute;
      width: 32px;
      height: 32px;
      left: 0;
      background: rgba(129, 129, 139, 0.1);
      border-radius: 50%;
    }
    &::before{
      content: '';
      position: absolute;
      background: url('@/assets/img/content/icons/list-icon.svg');
      width: 16px;
      height: 16px;
      left: 8px;
    }
  }
}
</style>
