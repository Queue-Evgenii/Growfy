<template>
  <div class="footer__lists flex">
    <div class="footer__list">
      <div class="footer__title">Pages</div>
      <ul class="footer__items">
        <li class="footer__item hover-underline" v-for="item in Pages" :key="item.name"><a :href="item.url" class="footer__link">{{ item.name }}</a></li>
      </ul>
    </div>
    <div class="footer__list">
      <div class="footer__title">Utility pages</div>
      <ul class="footer__items">
        <li class="footer__item hover-underline" v-for="item in UtilPages" :key="item.name"><a :href="item.url" class="footer__link">{{ item.name }}</a></li>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    Pages: {
      type: Array,
      required: true
    },
    UtilPages: {
      type: Array,
      required: true
    }
  }
}
</script>
