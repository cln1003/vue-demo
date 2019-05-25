<template>
  <div class="app">
    <router-view/>
    <Footer v-show="$route.meta.showFooter"/>
  </div>
</template>

<script>
import Footer from './components/Footer/Footer.vue'

export default {
  name: 'App',
  components: {
    Footer
  },
  mounted(){
    this.$store.dispatch('getHomeService')//首页服务
    this.$store.dispatch('getClassifyList')//顶部列表
  }
}
</script>

<style lang="stylus" rel="stylesheet/stylus" >
  .app
    height 100%
</style>
