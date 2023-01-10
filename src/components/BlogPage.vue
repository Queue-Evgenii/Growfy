<template>
  <div class="page__blog blog-page">
    <div class="blog-page__container _container">
      <div class="blog-page__rows">
        <div class="blog-page__row row-content__flexbox">
          <div class="blog-page__text-block content-block row-content__text-block">
            <span class="before-title">Blog</span>
            <h2 class="blog-page__title content-block__title row-content__title">Read our articles & news</h2>
            <p class="blog-page__text content-block__text row-content__text">Lorem ipsum dolor sit amet, consectetur adipiscing elit, suspendisse varius enim in eros elementum tristique. Duis cursus, mi quis viverra ornare, eros dolor.</p>
          </div>
          <div class="blog-page__button-block row-content__button-block">
            <div class="blog-page__button button content-block__button row-content__button">
              <router-link to="" class="blog-page__link">All Posts</router-link>
            </div>
          </div>
        </div>
        <div class="blog-page__row">
          <div class="blog-page__columns grid-columns">
            <router-link :to="item.url" class="blog-page__column grid-column" v-for="item in this.BlogItems" :key="item.id">
              <div class="blog-page__image">
                <img :src="item.image" alt="">
                <span class="blog-page__label">{{ item.label }}</span>
              </div>
              <div class="blog-page__blog-content">
                <div class="blog-page__blog-date">{{ item.date }}</div>
                <div class="blog-page__blog-title">{{ item.title }}</div>
                <div class="blog-page__blog-text">{{ item.text }}</div>
                <div class="blog-page__blog-link">Read now</div>
              </div>
            </router-link>
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
      BlogItems: [
        {
          url: '/',
          label: 'Social Media',
          image: require('@/assets/img/content/blog-img-1.png'),
          date: 'August 28, 2022',
          title: 'How to Use Social Proof in Marketing',
          text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit lobortis arcu enim urna adipiscing praesent velit viverra sit semper lorem.'
        },
        {
          url: '/',
          label: 'SEO',
          image: require('@/assets/img/content/blog-img-2.png'),
          date: 'August 28, 2022',
          title: 'Make a great first impression with these titles',
          text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit lobortis arcu enim urna adipiscing praesent velit viverra sit semper lorem.'
        },
        {
          url: '/',
          label: 'Strategy',
          image: require('@/assets/img/content/blog-img-3.png'),
          date: 'August 28, 2022',
          title: 'How to Grab Your Reader’s Attention',
          text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit lobortis arcu enim urna adipiscing praesent velit viverra sit semper lorem.'
        }
      ]
    }
  }
}
</script>
<style lang="scss">
.blog-page {
  &__rows {
    display: flex;
    flex-direction: column;
    row-gap: 64px;
  }
  &__image {
    width: 100%;
    min-width: 260px;
    height: 194px;
    position: relative;
    overflow: hidden;
    border-radius: 30px 30px 0px 0px;
    img {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: transform .2s ease 0s;
    }
  }
  &__label {
    position: absolute;
    bottom: 0;
    left: 0;
    padding: 9px 10px;
    background-color: rgba(129, 129, 139, 0.5);
    border-radius: 0px 10px 0px 0px;
    font-size: 14px;
    line-height: 22px;
    color: #FFFFFF;
  }
  &__column {
    &:hover{
      .blog-page__blog-title,
      .blog-page__blog-link{
        text-decoration: underline;
      }
      .blog-page__image{
        img{
          transform: scale(1.05);
        }
      }
    }
  }
  &__blog-content {
    display: flex;
    flex-direction: column;
    padding: 26px;
    row-gap: 20px;
  }
  &__blog-title {
    font-weight: 400;
    font-size: 19.2px;
    line-height: 27px;
    color: #FFFFFF;
  }
  &__blog-link {
    font-size: 14px;
    line-height: 22px;
    color: #3D96F4;
  }
}
</style>
