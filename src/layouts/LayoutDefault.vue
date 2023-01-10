<template>
  <div class="wrapper">
    <header class="header">
      <div class="header__container _container flex">
        <a href="/" class="header__logo">
          <img src="../assets/img/layouts/logo.png" alt="">
        </a>
        <div class="header__content flex">
          <HeaderMenu  v-if="MobileWidth" :HeaderMenu="this.HeaderMenu" />
          <div class="header__get-started button">
            <router-link to="/start">Get Started</router-link>
          </div>
        </div>
        <nav class="menu">
          <button v-bind:class="{active: burgerActive}" @click="burgerActive = !burgerActive" type="button" class="menu__icon icon-menu">
            <span></span>
            <span></span>
            <span></span>
          </button>
          <div v-bind:class="{active: burgerActive}" class="menu__body" >
            <HeaderMenu  v-if="!MobileWidth" :HeaderMenu="this.HeaderMenu" />
            <FooterLists v-if="!MobileWidth" :Pages="this.Pages" :UtilPages="this.UtilPages" />
          </div>
        </nav>
      </div>
    </header>
    <div class="pt"></div>
    <slot></slot>
    <footer class="footer">
      <div class="footer__container _container">
        <div class="footer__columns">
          <div class="footer__column">
            <a href="/" class="footer__logo">
              <img src="../assets/img/layouts/logo.png" alt="">
            </a>
            <div class="footer__text">Growfy is a template highly suitable for modern marketing agencies, digital studios, startups and businesses. The design is made in the dark style, which makes the site memorable and you can easily adapt it to your brand.</div>
            <ul class="footer__social-items flex">
              <li class="footer__social-item" v-for="item in this.Social" :key="item.url">
                <a :href="item.url" class="footer__social-link"><img :src="item.image" alt=""></a>
              </li>
            </ul>
          </div>
          <div class="footer__column">
            <FooterLists v-if="MobileWidth" :Pages="this.Pages" :UtilPages="this.UtilPages" />
          </div>
          <div class="footer__column">
            <div class="footer__title footer__title-no-margin">Subscribe to our newsletter</div>
            <div class="footer__text">Lorem ipsum dolor sit am consectetur adipiscing</div>
            <form action="" class="footer__form flex">
              <input type="text" name="email" id="email" placeholder="Enter your email">
              <input class="button" type="button" value="Subscribe">
            </form>
          </div>
        </div>
        <div class="footer__copy">© 2022</div>
      </div>
    </footer>
  </div>
</template>
<script>
import HeaderMenu from '@/components/header/HeaderMenu'
import FooterLists from '@/components/footer/FooterLists'
export default {
  data () {
    return {
      burgerActive: false,
      HeaderMenu: [
        {
          name: 'Home',
          url: '/'
        },
        {
          name: 'About',
          url: '/about'
        },
        {
          name: 'Pages',
          url: '/pages'
        },
        {
          name: 'Services',
          url: '/services'
        }
      ],
      Pages: [
        {
          name: 'Home',
          url: '/'
        },
        {
          name: 'About',
          url: '/about'
        },
        {
          name: 'Services',
          url: '/services'
        },
        {
          name: 'Packages',
          url: '/packages'
        },
        {
          name: 'Blog',
          url: '/blog'
        },
        {
          name: 'Contact',
          url: '/contact'
        }
      ],
      UtilPages: [
        {
          name: 'Instructions',
          url: '/instructions'
        },
        {
          name: 'Style guide',
          url: '/style-guide'
        },
        {
          name: 'Licenses',
          url: '/licenses'
        },
        {
          name: 'Changelog',
          url: '/changelog'
        },
        {
          name: 'Blog',
          url: '/blog'
        },
        {
          name: 'Password protected',
          url: '/password-protected'
        }
      ],
      Social: [
        {
          url: 'in',
          image: require('../assets/img/layouts/linked-icon.png')
        },
        {
          url: 'twitter',
          image: require('../assets/img/layouts/twitter-icon.png')
        },
        {
          url: 'facebook',
          image: require('../assets/img/layouts/facebook-icon.png')
        },
        {
          url: 'youtube',
          image: require('../assets/img/layouts/youtube-icon.png')
        },
        {
          url: 'instagram',
          image: require('../assets/img/layouts/inst-icon.png')
        }
      ]
    }
  },
  components: {
    HeaderMenu,
    FooterLists
  },
  computed: {
    MobileWidth () {
      if (window.innerWidth <= 720) {
        return false
      } else {
        return true
      }
    }
  },
  methods: {
  }
}
</script>
<style lang="scss">
.wrapper{
  background-color: #0D0D11;
  font-family: 'Poppins';
  font-weight: 300;
  font-size: 16px;
  line-height: 24px;
  color: #9C9C9C;
  overflow-x: hidden;
}
.menu{
  display: none;
  @media(max-width: 720px){
    display: block;
  }
  &__body{
    position: fixed;
    width: 100%;
    background: #0D0D11;
    z-index: 2;
    transition: all 0.5s ease 0s;
    left: 0;
    top: -1000%;
    overflow: auto;
    padding: 110px 30px 70px 30px;
    &.active{
      top: 0;
      box-shadow: 4px 4px 10px #0D0D11;
      overflow-y: visible;
    }
  }
  &__icon {
    display: none;
    @media(max-width: 992px){
      background: transparent;
      display: block;
      position: relative;
      flex: 0 0 28px;
      width: 28px;
      height: 20px;
      cursor: pointer;
      z-index: 3;
      background-color: transparent;
      span{
        transition: all 0.5s ease 0s;
        position: absolute;
        top: calc( 50% - 1.55px);
        left: 0;
        width: 100%;
        height: 3px;
        background-color: #3d3d3d;
        &:first-child{
          top: 0;
        }
        &:last-child{
          top: auto;
          bottom: 0;
        }
      }
      &.active{
        span{
          transform: scale(0);
          &:first-child{
            transform: rotate(-45deg);
            top: calc(50% - 2px);
          }
          &:last-child{
            transform: rotate(45deg);
            bottom: calc(50% - 1px);
          }
        }
      }
    }
  }
}
.pt{
  padding-top: 120px;
}
.header {
  position: fixed;
  width: 100%;
  background-color: #0D0D11;
  z-index: 10;
  &__container {
    padding-top: 32px;
    padding-bottom: 32px;
    column-gap: 32px;
  }
  &__logo {
    flex: 0 0 150px;
    z-index: 3;
  }
  &__content {
    flex: 1 1 auto;
    justify-content: right;
    column-gap: 32px;
  }
  &__get-started {
    min-width: 130px;
    width: 160px;
    z-index: 3;
    @media(max-width: 560px) {
      position: fixed;
      bottom: 30px;
      right: 15px;
      box-shadow: 2px 2px 15px #3D96F4;
    }
  }
}
.menu-header {
  color: #FFFFFF;
  margin: 0 -18px;
  flex-wrap: wrap;
  row-gap: 10px;
  justify-content: end;
  @media(max-width: 720px){
    justify-content: space-between;
    margin-bottom: 35px;
  }
  a{
    line-height: 26px;
    padding: 0 18px;
  }
  &__cart{
    white-space: nowrap;
    font-size: 17.6px;
    line-height: 28px;
    color: inherit;
    font-family: inherit;
    font-weight: inherit;
    padding: 0 18px;
    span{
      display: inline-flex;
      justify-content: center;
      align-items: center;
      width: 30px;
      height: 30px;
      margin-left: 5px;
      background: rgba(129, 129, 139, 0.3);
      border-radius: 100%;
    }
  }
}
.footer {
  &__container {
  }
  &__columns {
    display: flex;
    margin: 0 -32px;
    padding: 160px 0;
    row-gap: 60px;
    @media(max-width: 1100px) {
      flex-wrap: wrap;
    }
  }
  &__column {
    flex: 1 1 33.333%;
    display: flex;
    flex-direction: column;
    justify-content: start;
    padding: 0 32px;
    row-gap: 32px;
    min-width: 136px;
    @media(max-width: 1100px) {
      flex: 1 1 100%;
    }
  }
  &__logo {
  }
  &__text {
    line-height: 24px;
  }
  &__social-items {
    margin: 0 -8px;
  }
  &__social-item {
    padding: 0 8px;
  }
  &__lists {
    margin: 0 -10px;
    row-gap: 32px;
    @media(max-width: 920px){
      flex-wrap: wrap;
    }
  }
  &__list {
    flex: 1 1 50%;
    padding: 0 10px;
    line-height: 25.6px;
    white-space: nowrap;
  }
  &__title {
    line-height: 24px;
    margin-bottom: 32px;
    color: #fff;
    font-weight: 500;
  }
  &__title-no-margin {
    margin-bottom: 0;
  }
  &__items{
    display: flex;
    flex-direction: column;
    row-gap: 24px;
  }
  &__form {
    gap: 16px;
    input[type=text] {
      padding: 15px 33px;
      background-color: inherit;
      color: #999999;
      border: 1px solid rgba(129, 129, 139, 0.3);
      border-radius: 50px;
      flex: 1 1 225px;
      min-width: 136px;
      max-width: 225px;
    }
    input[type=button] {
      flex: 0 0 136px;
    }
    @media(max-width: 460px) {
      flex-wrap: wrap;
      input[type=text],
      input[type=button] {
        flex: 1 1 100%;
      }
      input[type=text]{
        max-width: 100%;
        min-width: none;
      }
    }
  }
  &__copy{
    border-top: 1px solid rgba(129, 129, 139, 0.2);
    padding: 47px 0;
    text-align: center;
  }
}
/* ==================================================== */
.button,
.secd-button{
  cursor: pointer;
  height: 52px;
  padding: 0 10px;
  color: #FFFFFF;
  border-radius: 50px;
  font-weight: 500;
  transition: all 0.2s ease 0s;
  a{
    display: flex;
    align-items: center;
    font-weight: 500;
    font-size: 14px;
    line-height: 22px;
    text-align: center;
    color: #FFFFFF;
    justify-content: center;
    height: 100%;
    width: 100%;
    padding: 0 10px;
  }
  &:hover{
    padding-bottom: 4px;
  }
}
.button{
  background-color: #3D96F4;
  &:hover{
    -webkit-box-shadow: 0px 2px 7px 1px #3D96F4;
    -moz-box-shadow: 0px 2px 7px 1px #3D96F4;
    box-shadow: 0px 2px 7px 1px #3D96F4;
  }
}
.secd-button{
  background-color: rgba(129, 129, 139, 0.2);
  &:hover{
    -webkit-box-shadow: 0px 2px 7px 1px rgba(129, 129, 139, 0.2);
    -moz-box-shadow: 0px 2px 7px 1px rgba(129, 129, 139, 0.2);
    box-shadow: 0px 2px 7px 1px rgba(129, 129, 139, 0.2);
  }
}
.title, .content-block__title {
  font-weight: 500;
  font-size: 51.2px;
  line-height: 61px;
  display: flex;
  align-items: center;
  color: #FFFFFF;
  @media(max-width: 620px) {
    font-size: 36px;
    line-height: 44px;
  }
}
.content-block__text {
  font-size: 18px;
  line-height: 27px;
}
.content-block{
  display: flex;
  flex-direction: column;
  row-gap: 15px;
  &__title {
  }
  &__text {
  }
  &__button {
    max-width: 160px;
    margin-top: 15px;
  }
}
.before-title {
  font-size: 10.8px;
  line-height: 17px;
  letter-spacing: 2px;
  text-transform: uppercase;
  padding: 11px 19px;
  border: 1px solid rgba(129, 129, 139, 0.2);
  border-radius: 12px;
  width: fit-content;
  margin-bottom: 5px;
}
.grid-columns{
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(360px, 1fr));
  gap: 48px;
  @media(max-width: 430px) {
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  }
}
.grid-column{
  display: flex;
  flex-direction: column;
  background-color: rgba(129, 129, 139, 0.1);
  border-radius: 30px;
  height: auto;
}
.row-content{
  &__flexbox {
    display: flex;
    gap: 30px;
    @media(max-width: 992px) {
      flex-direction: column;
    }
  }
  &__text-block {
    @media(min-width: 993px) {
      flex: 0 1 820px;
    }
  }
  &__button-block {
    @media(min-width: 993px) {
      flex: 1 1 auto;
      display: flex;
      align-items: end;
      justify-content: flex-end;
    }
  }
  &__button {
    flex: 1 1 160px;
    min-width: 130px;
  }
}
.decor{
  position: absolute;
  width: 122px;
  height: 122px;
  @media(max-width: 768px) {
    display: none;
  }
}
.hover-underline{
  &:hover{
    text-decoration: underline;
  }
}
.block-hover{
  transition: box-shadow 0.2s ease 0s;
  &:hover{
    box-shadow: 4px 4px 6px 0px rgba(129, 129, 139, 0.1);
  }
}
</style>
