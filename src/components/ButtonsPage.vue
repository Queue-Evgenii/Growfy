<template>
  <div class="buttons-page flex">
    <div class="buttons-page__button button">
      <router-link to="" class="buttons-page__link">Our services</router-link>
    </div>
    <div class="buttons-page__button secd-button">
      <router-link to="" class="buttons-page__link">Contact us</router-link>
    </div>
  </div>
</template>
<style lang="scss">
.buttons-page {
  column-gap: 32px;
  width: 100%;
  flex-wrap: wrap;
  row-gap: 15px;
  &__button {
    flex: 0 0 160px;
    // width: 160px;
    @media(max-width: 660px){
      flex: 1 1 100%;
    }
  }
  &__link {
  }
}
</style>
