<template>
  <div id="header">
    <div class="content">
      <div class="top">
        <slot name="left"></slot>
        <keep-alive>
          <div class="search" @click="jumpSeach('/search')">
            <i class="iconfont icon-search"></i>
            <span>搜索商品,共200000款好物</span>
          </div>
        </keep-alive>
        <slot name="right"></slot>
      </div>
      <div class="wrapCountent">
        <div class="wrapper" ref="wrap">
          <ul class="wrpContent" ref="tab" v-show="down">
            <li :class="{active:index===0}" v-for="(item,index) in kingKongList" :key="index">
              <a :href="item.schemeUrl">{{item.text}}</a>
            </li>
          </ul>
          <p class="wrp_span" v-show="!down">全部频道</p>
        </div>
        <div class="wrp_right">
          <div class="blank"></div>
          <div class="down" @click="down=!down">
            <i class="iconfont" :class="{'icon-xiangshang' : down,'icon-een':!down}"></i>
          </div>
        </div>
      </div>
    </div>
    <div class="channel" v-show="!down">
      <ul class="mask">
        <li :class="{active:index===0}" v-for="(item,index) in kingKongList" :key="index">
          {{item.text}}
        </li>
      </ul>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import BScroll from 'better-scroll'
  import {mapState} from 'vuex'
  export default {
    name: "headerNetease",
    data(){
      return {
        down: true
      }
    },
    mounted(){
      this.$nextTick(() => {
        new BScroll('.wrapper', {
          scrollX: true
        })
      })
    },
    computed: {
      ...mapState({
        kingKongList: state => state.classify.kingKongList
      })
    },
    methods: {
      jumpSeach(path){
        this.$router.replace(path)
      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>
  @import "../../commen/stylus/mixins.styl"
  #header
    background-color #fff
    position fixed
    top 0
    z-index 5
    .content
      height 148px
      width 750px
      .top
        display flex
        height 60px
        width 690px
        padding 15px 30px
        .neImg
          display inline-block
          background-image url("http://yanxuan-static.nosdn.127.net/hxm/yanxuan-wap/p/20161201/style/img/icon-normal/indexLogo-a90bdaae6b.png")
          background-size 138px 40px
          background-repeat no-repeat
          width 138px
          height 40px
        .search
          height 56px
          width 443px
          border-radius 10px
          background-color #eee
          margin-left 20px
          text-align center
          line-height 56px
          i
            vertical-align middle
            font-size 38px
          span
            color #666
        .login
          width 75px
          height 40px
          border 2px solid red
          border-radius 6px
          color red
          text-align center
          line-height 40px
          margin-left 16px
          margin-top 5px
      .wrapCountent
        height 70px
        width 750px
        display flex
        .wrapper
          width 651px
          height 60px
          overflow hidden
          margin-bottom 10px
          .wrpContent
            display flex
            margin-left 10px
            width 900px
            li
              text-align center
              height 60px
              width 143px
              line-height 60px
              white-space nowrap
              margin-left 42px
              font-size 26px
              a
                display inline-block
                height 100%
                width 100%
              &.active
                bottom-border-1px(#ab2b2b)
              &:first-child
                margin-left 30px
                bottom-border-1px(#FF0000)
          .wrp_span
            height 60px
            line-height 60px
            vertical-align middle
            margin-left 16px
            font-size 28px
            color black
        .wrp_right
          width 160px
          height 60px
          display flex
          .blank
            height 60px
            width 60px
            background-image linear-gradient(to right, rgba(255, 255, 255, 0) 0, #fff 100%)
          .down
            height 60px
            width 99px
            text-align center
            line-height 60px
            i
              font-size 26px
    .channel
      width 750px
      height 312px
      position absolute
      z-index 3
      background-color #fff
      .mask
        display flex
        flex-wrap wrap
        li
          text-align center
          line-height 56px
          font-size 24px
          width 150px
          height 56px
          border 1px solid #7e8c8d
          border-radius 8px
          margin-left 20px
          margin-bottom 30px
          margin-top 10px
          background-color #eee
          &.active
            border 1px solid red
            background-color #fff
</style>
