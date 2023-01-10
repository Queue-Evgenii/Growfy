<template>
  <div class="page__offer offer-page">
    <div class="offer-page__container _container">
      <div class="offer-page__columns flex block-hover">
        <div class="offer-page__column flex">
          <div class="offer-page__title">Ready to start scaling your business now?</div>
          <div class="offer-page__text">Lorem ipsum dolor sit am consectetur adipiscing varius enim in eros.</div>
        </div>
        <div class="offer-page__column flex">
          <ButtonsPage />
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
.offer-page {
}
.offer-page__columns {
  background: rgba(129, 129, 139, 0.1);
  border-radius: 30px;
  flex-wrap: wrap;
  padding: 52px 40px;
  justify-content: space-between;
  row-gap: 32px;
  @media(max-width: 420px) {
    padding: 42px 20px;
  }
}
.offer-page__column {
  flex-direction: column;
  justify-content: center;
  text-align: center;
  padding: 0 40px;
  flex: 1 1 50%;
  .buttons-page{
    justify-content: center;
  }
  @media(max-width: 768px) {
    flex: 1 1 100%;
  }
  @media(max-width: 420px) {
    padding: 0 20px;
  }
}
.offer-page__title {
  font-weight: 400;
  font-size: 32px;
  line-height: 45px;
  color: #FFFFFF;
  @media(max-width: 420px) {
    font-size: 25px;
  }
}
</style>
