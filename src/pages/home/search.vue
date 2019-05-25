<template>
  <div class="searchCountend">
    <div class="searchHeader">
      <div class="searchCenter">
        <div class="searchForm">
          <div class="searchInput">
            <i class="searchIcon"></i>
            <input type="text" placeholder="瑞士制造 玫瑰腕表上新疯抢" v-model="massage">
            <i class="scarchClose" v-show="massage" @click="handleClose"></i>
          </div>
        </div>
        <span class="searchPass" @click="$router.replace('/home')">取消</span>
      </div>
    </div>
    <div class="searchPopular" v-show="!massage">
      <div class="searchHistory" v-show="massageArr.length">
        <div class="historyHeader">
          <span class="searchLeft">历史记录</span>
          <span class="iconfont icon-laji" @click="Rubbish"></span>
        </div>
        <ul>
          <li v-for="(item,index) in massageArr">{{item}}</li>
        </ul>
      </div>
      <div class="popularContend">
        <p>热门搜索</p>
        <ul class="popularItem">
          <li :class="{active:index===hotIndex}" v-for="(item,index) in hotList" :key="index" @click="handleHot(index)">
            {{item.keyword}}
          </li>
        </ul>
      </div>
    </div>
    <div class="searchHide" v-show="massage">
      <ul v-show="searchList">
        <li v-for="(item,index) in searchList" :key="index">{{item}}</li>
      </ul>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import {mapState} from 'vuex'
  import stroge from '../../until/strogeUnti'
  export default {
    name: "searchCountend",
    data(){
      return {
        massage: '',//input中的值
        hotIndex: 0,//点击当前index
        massageArr: []//内存中存储的数据
      }
    },
    computed: {
      ...mapState({
        searchList: state => state.search.searchList,
        hotList: state => state.search.hotList
      })
    },

    mounted(){
      if(this.massageArr.length){
        this.massageArr=stroge.getStroge()
      }else {
        this.massageArr=[]
      }
      this.$store.dispatch('getReqHot')
    },
    methods: {
      handleClose(){
        this.massage = ''
      },
      handleHot(index){
        this.hotIndex = index
      },
      Rubbish(){
        stroge.moveStroge()
        this.massageArr = ''
      }
    },
    watch: {
      massage(val){
        if (val.split(" ").join("").length == 0) {
          return
        }
        this.$store.dispatch('getMassage', val)
        console.log(val,'val');
        this.massageArr.push(val)
        stroge.setStroge(this.massageArr)
        this.massageArr=stroge.getStroge()

      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>
  .searchCountend
    width 100%
    height 100%
    background-color #7e8c8d
    .searchHeader
      width 750px
      height 87px
      background-color #fff
      .searchCenter
        width 690px
        height 89px
        padding 0px 30px
        display flex
        line-height 89px
        .searchForm
          width 604px
          height 56px
          line-height 88px
          .searchInput
            width 100%
            height 100%
            background-color #eee
            margin-top 10px
            display flex
            position relative
            input
              width 100%
              height 98%
              font-size 28px
              background-color #eee
              margin-left 50px
              outline none
              vertical-align middle
            .searchIcon
              position absolute
              top -10px
              left 10px
              height 28px
              width 28px
              vertical-align middle
              &::before
                content ''
                width 100%
                height 100%
                display inline-block
                margin-right 16px
                background-image url('//yanxuan-static.nosdn.127.net/hxm/yanxuan-wap/p/20161201/style/img/icon-normal/search2-553dba3aff.png')
                background-repeat no-repeat

            .scarchClose
              background-image url("//yanxuan-static.nosdn.127.net/hxm/yanxuan-wap/p/20161201/style/img/icon-normal/clearIpt-0821f71561.png")
              display inline-block
              width 50px
              height 50px
              position absolute
              top 0px
              right 0px
        .searchPass
          width 60px
          height 41px
          margin-left 30px
          margin-top 15px
          display inline-block
          font-size 26px
          text-align center
          line-height 41px
    .searchPopular
      width 100%
      height auto
      background-color #fff
      .searchHistory
        width 690px
        height 137px
        padding 0px 30px 30px
        margin-bottom 20px
        .historyHeader
          width 690px
          height auto
          font-size 28px
          line-height 90px
          color #999
          span
            &:last-child
              float right
              font-size 30px
        ul
          width 690px
          height 79px
          display flex
          flex-wrap wrap
          li
            height 45px
            width 72px
            line-height 45px
            padding 1px 15px
            margin 0px 32px 32px 0px
            border 1px solid #999
            border-radius 6px
      .popularContend
        width 690px
        height auto
        padding 0px 30px 30px
        margin-bottom 20px
        p
          width 100%
          height 90px
          line-height 90px
          color #999
        .popularItem
          width 720px
          height 237px
          margin 0px 30px 30px 0
          display flex
          flex-wrap wrap
          li
            border 1px solid #999
            width auto
            height 45px
            padding 1px 15px
            margin-right 32px
            margin-bottom 32px
            text-align center
            line-height 45px
            &.active
              border 1px solid #b4282d
              color #b4282d

    .searchHide
      width 100%
      height auto
      background-color #fff
      padding-left 30px
      ul
        li
          height 90px
          width 720px
          line-height 90px
          font-size 30px
          border-bottom 1px solid #d9d9d9

</style>
