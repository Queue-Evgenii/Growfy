<template>
  <LayoutDefault>
    <main class="page">
      <PreviewPage />
      <TrustedSlider />
      <ServicesPage />
      <ChoosePage />
      <StatisticPage />
      <ClientsReview />
      <BlogPage />
      <OfferPage />
    </main>
  </LayoutDefault>
</template>
<script>
import LayoutDefault from '@/layouts/LayoutDefault'
import PreviewPage from '@/components/PreviewPage'
import TrustedSlider from '@/components/TrustedSlider'
import ServicesPage from '@/components/ServicesPage'
import ChoosePage from '@/components/ChoosePage'
import StatisticPage from '@/components/StatisticPage'
import ClientsReview from '@/components/ClientsReview'
import BlogPage from '@/components/BlogPage'
import OfferPage from '@/components/OfferPage'
export default {
  components: {
    LayoutDefault,
    PreviewPage,
    TrustedSlider,
    ServicesPage,
    ChoosePage,
    StatisticPage,
    ClientsReview,
    BlogPage,
    OfferPage
  }
}
</script>
<style lang="scss">
.page{
  display: flex;
  flex-direction: column;
  row-gap: 190px;
  padding: 20px 0 80px 0;
}
</style>
