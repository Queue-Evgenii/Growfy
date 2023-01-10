<template>
  <div class="page__preview preview-page">
    <div class="preview-page__container _container">
      <div class="preview-page__columns">
        <div class="preview-page__column preview-page__content">
          <h1 class="preview-page__title title">Marketing solutions that grow your business.</h1>
          <p class="preview-page__text text">Lorem ipsum dolor sit amet, consectetur adipiscing elit, suspendisse varius enim in eros elementum tristique. Duis cursus, mi quis viverra ornare, eros dolor.</p>
          <ButtonsPage />
          <img src="@/assets/img/content/decor.png" alt="" class="preview-page__decor decor">
        </div>
        <div class="preview-page__column preview-page__images images-preview">
          <div class="images-preview__columns flex">
            <div class="images-preview__column flex">
              <div class="images-preview__image-big"><img src="@/assets/img/content/review-green.png" alt=""></div>
              <div class="images-preview__image-small"><img src="@/assets/img/content/review-yellow.png" alt=""></div>
            </div>
            <div class="images-preview__column flex">
              <div class="images-preview__image-small"><img src="@/assets/img/content/review-orange.png" alt=""></div>
              <div class="images-preview__image-big"><img src="@/assets/img/content/review-blue.png" alt=""></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import ButtonsPage from '@/components/ButtonsPage'
export default {
  components: {
    ButtonsPage
  }
}
</script>
<style lang="scss">
.preview-page {
  &__decor{
    top: 102px;
    left: -20px;
    @media(max-width: 992px) {
      top: 85px;
      left: -15px;
    }
  }
  &__columns {
    display: flex;
    align-items: flex-start;
    gap: 32px;
  }
  &__column {
    flex: 1 1 50%;
  }
  &__content {
    position: relative;
    padding-top: 120px;
    padding-right: 115px;
    display: flex;
    flex-direction: column;
    row-gap: 32px;
    @media(max-width: 1130px) {
      padding-top: 50px;
      padding-right: 50px;
    }
    @media(max-width: 992px){
      flex: 1 1 auto;
      padding-right: 70px;
    }
    @media(max-width: 768px){
      padding: 0;
    }
    @media(max-width: 620px){
      row-gap: 25px
    }
  }
  &__images{
    @media(max-width: 768px){
      display: none;
    }
  }
}
.images-preview {
  &__columns {
    column-gap: 60px;
    @media(max-width: 1130px) {
      column-gap: 30px;
    }
  }
  &__column {
    flex-direction: column;
    row-gap: 32px;
    @media(max-width: 1130px) {
      row-gap: 15px;
    }
    @media(max-width: 992px) {
      &:last-child{
        display: none;
      }
    }
  }
  &__image-big,
  &__image-small {
    position: relative;
    img{
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
    }
  }
  &__image-big{
    width: 242px;
    height: 423px;
    @media(max-width: 1130px) {
      width: 202px;
      height: 363px;
    }
  }
  &__image-small {
    width: 242px;
    height: 242px;
    @media(max-width: 1130px) {
      width: 202px;
      height: 202px;
    }
  }
}
</style>
