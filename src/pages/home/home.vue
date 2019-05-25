<template>
  <div class="home">
    <Header>
      <span class="neImg" slot="left"></span>
      <span class="login" slot="right">登录</span>
    </Header>
    <div class="swiper-container">
      <ul class="swiper-wrapper">
        <li class="swiper-slide">
          <img
            src="https://yanxuan.nosdn.127.net/cfa93449e6deef735fc746c7aa39b96f.jpg?imageView&amp;quality=75&amp;thumbnail=750x0"
            alt="网易">
        </li>
        <li class="swiper-slide">
          <img
            src="https://yanxuan.nosdn.127.net/931e7f847284a387d4725c9409383814.jpg?imageView&amp;quality=75&amp;thumbnail=750x0"
            alt="网易">
        </li>
        <li class="swiper-slide">
          <img
            src="https://yanxuan.nosdn.127.net/ac28c333645667553b74545c46ba5e7b.jpg?imageView&amp;quality=75&amp;thumbnail=750x0"
            alt="网易">
        </li>
        <li class="swiper-slide">
          <img
            src="https://yanxuan.nosdn.127.net/a1d68b48382e83619dc00e5d1287f2ed.jpg?imageView&amp;quality=75&amp;thumbnail=750x0"
            alt="网易">
        </li>
        <li class="swiper-slide">
          <img
            src="https://yanxuan.nosdn.127.net/cfdb199489776e89c782eae519645f2f.jpg?imageView&amp;quality=75&amp;thumbnail=750x0"
            alt="网易">
        </li>
        <li class="swiper-slide">
          <img
            src="https://yanxuan.nosdn.127.net/a7b08e3aed13787da15c58879963be01.jpg?imageView&amp;quality=75&amp;thumbnail=750x0"
            alt="网易">
        </li>
        <li class="swiper-slide">
          <img
            src="https://yanxuan.nosdn.127.net/68f443a9bcc78b0c46a414a633f66c47.jpg?imageView&amp;quality=75&amp;thumbnail=750x0"
            alt="网易">
        </li>
        <li class="swiper-slide">
          <img
            src="https://yanxuan.nosdn.127.net/931e7f847284a387d4725c9409383814.jpg?imageView&amp;quality=75&amp;thumbnail=750x0"
            alt="网易">
        </li>
      </ul>
      <div class="swiper-pagination"></div>
    </div>
    <div class="indexService">
      <div class="policy">
        <ul class="policyItem">
          <li v-for="(item,index) in policyDesc" :key="index">
            <a href="javascript:;">
              <img :src="item.icon" alt="">
              <span>{{item.desc}}</span>
            </a>
          </li>
        </ul>
      </div>
    </div>
    <div class="slide">
      <ul class="slide-list">
        <li v-for="(item,index) in kingKongList" :key="index">
          <img class="img" :src="item.picUrl">
          <span>{{item.text}}</span>
        </li>
      </ul>
    </div>
    <div class="purchase">
      <img src="https://yanxuan.nosdn.127.net/02c975c2c8ef58225f1acafea7d41152.png" class="img">
    </div>
    <ul class="guide-list">
      <li class="item1">
        <h3>性价比之王</h3>
        <p>品质惊人的良心代替</p>
        <div class="iteml-img">
          <img
            src="https://yanxuan.nosdn.127.net/b097972db0ed9d5b47fbed0e2dbd1d99.png?imageView&thumbnail=150x150&quality=75"
            alt="">
          <img
            src="https://yanxuan.nosdn.127.net/b093cd15ca7de193d46f0ac44dde71da.png?imageView&thumbnail=150x150&quality=75"
            alt="">
        </div>
      </li>
      <li class="item1">
        <h3>性价比之王</h3>
        <p>品质惊人的良心代替</p>
        <div class="iteml-img">
          <img
            src="https://yanxuan.nosdn.127.net/b097972db0ed9d5b47fbed0e2dbd1d99.png?imageView&thumbnail=150x150&quality=75"
            alt="">
          <img
            src="https://yanxuan.nosdn.127.net/b093cd15ca7de193d46f0ac44dde71da.png?imageView&thumbnail=150x150&quality=75"
            alt="">
        </div>
      </li>
      <li class="item1">
        <h3>性价比之王</h3>
        <p>品质惊人的良心代替</p>
        <div class="iteml-img">
          <img
            src="https://yanxuan.nosdn.127.net/b097972db0ed9d5b47fbed0e2dbd1d99.png?imageView&thumbnail=150x150&quality=75"
            alt="">
          <img
            src="https://yanxuan.nosdn.127.net/b093cd15ca7de193d46f0ac44dde71da.png?imageView&thumbnail=150x150&quality=75"
            alt="">
        </div>
      </li>
      <li class="item1">
        <h3>性价比之王</h3>
        <p>品质惊人的良心代替</p>
        <div class="iteml-img">
          <img
            src="https://yanxuan.nosdn.127.net/b097972db0ed9d5b47fbed0e2dbd1d99.png?imageView&thumbnail=150x150&quality=75"
            alt="">
          <img
            src="https://yanxuan.nosdn.127.net/b093cd15ca7de193d46f0ac44dde71da.png?imageView&thumbnail=150x150&quality=75"
            alt="">
        </div>
      </li>
    </ul>
    <div class="personalTailorModule">
      <div class="categoryModule">
        <div class="categoryItem">
          <a href="javascript:;"></a>
          <div class="categoryWrp">
            <div class="wrapper" ref="wrap">
              <ul class="wrpContent" ref="tab">
                <li>
                  <div class="wrpItem">
                    <div class="wrpImg">
                      <img
                        src="https://yanxuan.nosdn.127.net/d9376c059ce15a774199e2cedc5a8d63.png?imageView&quality=65&thumbnail=330x330"
                        alt="">
                    </div>
                    <div class="wrpHide">
                      <span>999+好评爆款，洁齿又护龈</span>
                    </div>
                  </div>
                  <div class="wrpPrice">
                    <p style="color: #333">全净皓齿变速式声波电动牙刷</p>
                    <p class="price">￥179<span>￥290</span></p>
                    <div class="preferential"><span>520特惠</span></div>
                  </div>
                </li>
                <li>
                  <div class="wrpItem">
                    <div class="wrpImg">
                      <img
                        src="https://yanxuan.nosdn.127.net/d9376c059ce15a774199e2cedc5a8d63.png?imageView&quality=65&thumbnail=330x330"
                        alt="">
                    </div>
                    <div class="wrpHide">
                      <span>999+好评爆款，洁齿又护龈</span>
                    </div>
                  </div>
                  <div class="wrpPrice">
                    <p>全净皓齿变速式声波电动牙刷</p>
                    <p>￥179</p>
                    <span>520特惠</span>
                  </div>
                </li>
                <li>
                  <div class="wrpItem">
                    <div class="wrpImg">
                      <img
                        src="https://yanxuan.nosdn.127.net/d9376c059ce15a774199e2cedc5a8d63.png?imageView&quality=65&thumbnail=330x330"
                        alt="">
                    </div>
                    <div class="wrpHide">
                      <span>999+好评爆款，洁齿又护龈</span>
                    </div>
                  </div>
                  <div class="wrpPrice">
                    <p>全净皓齿变速式声波电动牙刷</p>
                    <p>￥179</p>
                    <span>520特惠</span>
                  </div>
                </li>
                <li>
                  <div class="wrpItem">
                    <div class="wrpImg">
                      <img
                        src="https://yanxuan.nosdn.127.net/d9376c059ce15a774199e2cedc5a8d63.png?imageView&quality=65&thumbnail=330x330"
                        alt="">
                    </div>
                    <div class="wrpHide">
                      <span>999+好评爆款，洁齿又护龈</span>
                    </div>
                  </div>
                  <div class="wrpPrice">
                    <p>全净皓齿变速式声波电动牙刷</p>
                    <p>￥179</p>
                    <span>520特惠</span>
                  </div>
                </li>
                <li>
                  <div class="wrpItem">
                    <div class="wrpImg">
                      <img
                        src="https://yanxuan.nosdn.127.net/d9376c059ce15a774199e2cedc5a8d63.png?imageView&quality=65&thumbnail=330x330"
                        alt="">
                    </div>
                    <div class="wrpHide">
                      <span>999+好评爆款，洁齿又护龈</span>
                    </div>
                  </div>
                  <div class="wrpPrice">
                    <p>全净皓齿变速式声波电动牙刷</p>
                    <p>￥179</p>
                    <span>520特惠</span>
                  </div>
                </li>
                <li>
                  <div class="wrpItem">
                    <div class="wrpImg">
                      <img
                        src="https://yanxuan.nosdn.127.net/d9376c059ce15a774199e2cedc5a8d63.png?imageView&quality=65&thumbnail=330x330"
                        alt="">
                    </div>
                    <div class="wrpHide">
                      <span>999+好评爆款，洁齿又护龈</span>
                    </div>
                  </div>
                  <div class="wrpPrice">
                    <p>全净皓齿变速式声波电动牙刷</p>
                    <p>￥179</p>
                    <span>520特惠</span>
                  </div>
                </li>
                <li>
                  <div class="wrpItem">
                    <div class="wrpImg">
                      <img
                        src="https://yanxuan.nosdn.127.net/d9376c059ce15a774199e2cedc5a8d63.png?imageView&quality=65&thumbnail=330x330"
                        alt="">
                    </div>
                    <div class="wrpHide">
                      <span>999+好评爆款，洁齿又护龈</span>
                    </div>
                  </div>
                  <div class="wrpPrice">
                    <p>全净皓齿变速式声波电动牙刷</p>
                    <p>￥179</p>
                    <span>520特惠</span>
                  </div>
                </li>
                <li>
                  <div class="wrpItem">
                    <div class="wrpImg">
                      <img
                        src="https://yanxuan.nosdn.127.net/d9376c059ce15a774199e2cedc5a8d63.png?imageView&quality=65&thumbnail=330x330"
                        alt="">
                    </div>
                    <div class="wrpHide">
                      <span>999+好评爆款，洁齿又护龈</span>
                    </div>
                  </div>
                  <div class="wrpPrice">
                    <p>全净皓齿变速式声波电动牙刷</p>
                    <p>￥179</p>
                    <span>520特惠</span>
                  </div>
                </li>
                <li>
                  <div class="wrpItem">
                    <div class="wrpImg">
                      <img
                        src="https://yanxuan.nosdn.127.net/d9376c059ce15a774199e2cedc5a8d63.png?imageView&quality=65&thumbnail=330x330"
                        alt="">
                    </div>
                    <div class="wrpHide">
                      <span>999+好评爆款，洁齿又护龈</span>
                    </div>
                  </div>
                  <div class="wrpPrice">
                    <p>全净皓齿变速式声波电动牙刷</p>
                    <p>￥179</p>
                    <span>520特惠</span>
                  </div>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
      <div class="ftWrap">
        <div class="ftItem">
          <div class="ftEdition">
            <div class="edition-left">下载APP</div>
            <div class="edition-right">电脑版</div>
          </div>
          <p>网易公司版权所有@1997-2019</p>
          <p>网易经营许可证：JY13301080111719</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import Header from '../../components/Header/Header.vue'
  import Swiper from 'swiper'
  import 'swiper/dist/css/swiper.css'
  import BScroll from 'better-scroll'
  import {mapState} from 'vuex'
  export default {
    name: "home",
    data(){
      return {
        down: true
      }
    },
    methods: {
      personScroll() {
        // 默认有六个li子元素，每个子元素的宽度为120px
//        let width = 9 * 200;
//        this.$refs.tab.style.width = width + "px";
        // this.$nextTick 是一个异步函数，为了确保 DOM 已经渲染
        this.$nextTick(() => {
          if (!this.scroll) {
            this.scroll = new BScroll(this.$refs.wrap, {

              click: true,
              scrollX: true,
              // 忽略竖直方向的滚动
              scrollY: false,
              eventPassthrough: "vertical"
            })
          } else {
            this.scroll.refresh()
          }
        })
      }
    },
    created() {
      this.$nextTick(() => {
        this.personScroll()
      })
    },
    components: {
      Header
    },
    computed: {
      ...mapState({
        policyDesc: state => state.shop.policyDescList,
        kingKongList: state => state.classify.kingKongList
      })
    },
    mounted(){
      new Swiper('.swiper-container', {
        autoplay: true,
        loop: true,
        pagination: {
          el: '.swiper-pagination',
          clickable: true
        }
      })
    }

  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  @import "../../commen/stylus/mixins.styl"
  .home
    margin-top 158px
    padding-bottom 100px
    img
      width 750px
      height 370px
    .swiper-pagination-bullets
      bottom 50px !important
    .swiper-pagination-bullet
      width 42px
      height 4px
      border-radius 0px
    .swiper-pagination-bullet-active
      background-color #fff
    .indexService
      height 72px
      width 750px
      line-height 72px
      .policy
        width 700px
        padding-left 25px
        padding-right 25px
        font-size 24px
        color #B4282D
        display flex
        justify-content space-around
        .policyItem
          width 690px
          height 72px
          padding 0 30px
          display flex
          li
            width 228px
            height 36px
            img
              width 32px
              height 32px
              vertical-align middle
            span
              vertical-align middle
              color #B4282D

    .slide
      width 750px
      height 341px
      font-size 24px
      .slide-list
        display flex
        flex-wrap: wrap
        width 750px
        height 341px
        li
          width 110px
          height 156px
          margin 20px 20px 0px 20px
          img
            width 100%
            height 110px
            margin-top -5px

    .purchase
      width 750px
      height 160px
      margin-top 10px
      margin-bottom 10px
      .img
        width 100%
        height 100%
    .guide-list
      box-sizing border-box
      display flex
      flex-wrap wrap
      width 750px
      height 576px
      padding 5px 30px 10px 30px
      .item1
        box-sizing border-box
        padding 20px
        width 343px
        height 264px
        border-right 1px solid #fff
        background-image url("https://yanxuan.nosdn.127.net/b143c18172b5433310ff1f2adf281792.png?imageView&thumbnail=343x264&quality=75")
        h3
          font-size 36px
          margin-bottom 8px
        .iteml-img
          img
            width 150px
            height 150px
            float left
    .personalTailorModule
      position relative
      width 750px
      height 1000px
      .categoryModule
        width 750px
        .categoryItem
          width 100%
          height 781px
          a
            display inline-block
            height 370px
            width 100%
            background-image url(https://yanxuan.nosdn.127.net/c0a49c73e5c8cd794be7a7c3a9c80cca.jpg?imageView&thumbnail=750x0&quality=75)
            background-size 100% 100%
          .categoryWrp
            width 750px
            height 391px
            .wrapper
              width 690px
              height 361px
              padding 0px 30px 30px 30px
              margin-top 20px
              display flex
              overflow hidden
              .wrpContent
                height 361px
                display flex
                li
                  height 361px
                  margin-left 30px
                  .wrpItem
                    width 200px
                    height 200px
                    margin-bottom 12px
                    background-color #eee
                    position relative
                    .wrpImg
                      width 200px
                      height 200px
                      img
                        width 100%
                        height 100%

                    .wrpHide
                      width 180px
                      height 36px
                      padding 6px 10px
                      color #9F8A60
                      background-color #F1ECE2
                      position absolute
                      bottom 0px
                      left 0px
                      white-space nowrap
                      overflow hidden
                      span
                        line-height 36px
                        margin-left 15px

                  .wrpPrice
                    width 200px
                    height auto
                    .price
                      margin-top 8px
                      color red
                      span
                        color #999
                        text-decoration line-through

                    .preferential
                      width 200px
                      height 33px
                      span
                        display inline-block
                        border 1px solid red
                        color red
                        text-align center
                        line-height 30px
                        height 30px
                        width 100px
                        border-radius 15px

      .ftWrap
        position absolute
        bottom 0px
        width 750px
        height 245px
        background-color #414141
        .ftItem
          width 710px
          height 162px
          padding 54px 20px 28px 20px
          text-align center
          color #fff
          .ftEdition
            width 710px
            height 62px
            margin-bottom 36px
            display flex
            justify-content center
            div
              border 1px solid #999
              width 172px
              height 62px
              text-align center
              line-height 62px
            .edition-left
              margin-right 50px
          p
            margin-bottom 5px
            color #999


</style>
