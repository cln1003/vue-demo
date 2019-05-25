<template>
  <footer class="footerContent border-1px">
    <a href="javascript:;" class="footer_item" :class="{on:$route.path === '/home'}" @click="goto('/home')">
      <i class="iconfont icon-home"></i>
      <span>首页</span>
    </a>
    <a href="javascript:;" class="footer_item" :class="{on: /^classify/.test($route.path)}" @click="goto('/classify')">
      <i class="iconfont icon-Class"></i>
      <span>分类</span>
    </a>
    <a href="javascript:;" class="footer_item" :class="{on:$route.path === '/know'}" @click="goto('/know')">
      <i class="iconfont icon-shihuo"></i>
      <span>识物</span>
    </a>
    <a href="javascript:;" class="footer_item" :class="{on:$route.path === '/shop'}" @click="goto('/shop')">
      <i class="iconfont icon-gouwuche2"></i>
      <span>购物车</span>
    </a>
    <a href="javascript:;" class="footer_item" :class="{on:$route.path === '/person'}" @click="goto('/person')">
      <i class="iconfont icon-user-1"></i>
      <span>个人</span>
    </a>
  </footer>
</template>

<script type="text/ecmascript-6">
  export default {
    name: "footerShop",
    methods:{
      goto(path){
        this.$router.replace(path)
      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>
  @import "../../commen/stylus/mixins.styl"
  .footerContent
    top-border-1px(#e4e4e4)
    position fixed
    background-color #eee
    bottom 0px
    right 0px
    left 0px
    width 750px
    height 100px
    display flex
    justify-content space-around
    .footer_item
      display flex
      flex-direction column
      width 150px
      height 75px
      margin-top 6px
      text-align center
      align-items center
      color #999999
      font-size 28px
      &.on
        color red
      span
        display block
        color black
        margin-top 6px
        height 31px
      i
        display inline-block
        font-size 48px

</style>
