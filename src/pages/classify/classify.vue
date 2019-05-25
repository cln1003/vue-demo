<template>
  <div class="classify">
    <div class="classHeader">
      <div class="search" @click="$router.push('/search')">
        <i class="iconfont icon-search"></i>
        <span>搜索商品,共200000款好物</span>
      </div>
    </div>
    <div class="classifyCount">
      <div class="menu-wrapper">
        <ul ref="leftUl" class="leftUl">
          <li
            @click="isShow(item)"
            class="menu-item" v-for="(item,index) in subCateList" :key="item.id">
            <span class="text" :class="{current:currentIndex===item.id}"><i class="current"></i>{{item.name}}</span>
          </li>
        </ul>
      </div>
      <router-view></router-view>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import Header from '../../components/Header/Header.vue'
  import BScroll from 'better-scroll'
  import {mapState} from 'vuex'
  export default {
    name: "classify",
    data(){
      return{
        currentIndex:0
      }
    },
    computed: {
      ...mapState({
        subCateList: state => state.classify.subCateList
      }),
    },
    mounted(){
      new BScroll('.menu-wrapper')
      this.$store.dispatch('getSubCateList',()=>{
        this.currentIndex=this.subCateList[0].id
        this.$router.push(`/classify/${this.currentIndex}`)
      })
    },

    methods: {
      isShow(item){
        this.$router.push({path:`/classify/${(item.id)}`})
        return this.currentIndex = item.id
      }
    }

  }
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>
  @import "../../commen/stylus/mixins.styl"
  .classify
    width 750px
    height auto
    margin-bottom 100px
    .classHeader
      width 690px
      height 90px
      padding 0px 30px
      .search
        margin-top 10px
        height 56px
        width 100%
        border-radius 10px
        background-color #eee
        text-align center
        line-height 56px
        i
          vertical-align middle
          font-size 38px
        span
          color #666

    .classifyCount
      display flex
      width 100%
      height 900px
      background #fff
      overflow hidden
      border-top 1px solid black
      .menu-wrapper
        flex 0 0 162px
        width 162px
        height 900px
        .leftUl
          padding 40px 0px
          width 162px
          position relative
          .menu-item
            display table
            height 50px
            width 162px
            margin-top 40px
            text-align center
            &:first-child
              margin-top 0px
            .text
              display table-cell
              width 162px
              vertical-align middle
              font-size 32px
              vertical-align middle
              &.current
                color #ab2b2b
                &::before
                  content ''
                  display inline-block
                  float left
                  width 5px
                  height 45px
                  background #ab2b2b
</style>
