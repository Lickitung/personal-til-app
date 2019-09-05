<template>
  <div>
    <Header @sidenavToggle="displaySidenav = !displaySidenav"/>
    <SideNav 
    :show="displaySidenav" 
    @close="displaySidenav = false"/>
    <nuxt />
  </div>
</template>

<script>
import Header from '@/components/Navigation/Header'
import SideNav from '@/components/Navigation/SideNav'

export default {
  components: {
    Header,
    SideNav
  },
  data() {
    return {
      displaySidenav: false
    }
  }
}
</script>

<style>
html {
  font-family: 'Chilanka', sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

</style>
