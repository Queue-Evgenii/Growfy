<template>
  <nav class="header__menu menu-header flex">
    <router-link class="hover-underline" v-for="item in HeaderMenu" :key="item.name" :to="item.url">{{ item.name }}</router-link>
    <button class="menu-header__cart hover-underline">Cart<span>0</span></button>
  </nav>
</template>
<script>
export default {
  props: {
    HeaderMenu: {
      type: Array,
      required: true
    }
  }
}
</script>
