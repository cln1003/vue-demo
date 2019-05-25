<template>
  <div class="classifyCenter">
    <div class="classifyItem" v-if="subArr">
      <div class="classifyImg" >
        <img :src="subArr.bannerUrl" alt="">
      </div>
      <div class="classifyList">
        <ul class="classifySub">
          <li v-for="(item,index) in subArr.subCateList" :key="index" class="itemOne">
            <a href="javascript:;">
              <img :src="item.wapBannerUrl" alt="">
              <div class="itemText">{{item.name}}</div>
            </a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import {mapState} from 'vuex'
  import BScroll from 'better-scroll'
  export default {
    name: "classifyItem",
    data(){
      return {
        subArr: []
      }
    },
    computed: {
      getId(){
        return this.$route.params.id
      },
      ...mapState({
        subCateList: state => state.classify.subCateList
      })
    },
    mounted(){
      new BScroll('.classifyCenter',{
        scrollY: true
      })
      this.subArr = this.subCateList.find(item => {
        console.log(this.getId);
        return item.id === this.getId * 1
      })
    },
    watch: {
      getId(){
        this.subArr = this.subCateList.find(item => {
          console.log(this.getId);
          return item.id === this.getId * 1
        })
      },
      subCateList(){
        this.subArr = this.subCateList.find(item => {
          console.log(this.getId);
          return item.id === this.getId * 1
        })
      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>
  .classifyCenter
    height 900px
    width 528px
    padding 30px 30px 21px
    overflow hidden
    .classifyItem
      width 528px
      .classifyImg
        width 528px
        height 192px
        margin-bottom 20px
        img
          width 100%
          height 100%
      .classifyList
        width 528px
        height auto
        .classifySub
          width 100%
          height 100%
          display flex
          flex-wrap wrap
          .itemOne
            width 144px
            height 216px
            margin-right 24px
            &:nth-child(3n)
              margin-right 0
            img
              display inline-block
              width 144px
              height 144px

</style>
