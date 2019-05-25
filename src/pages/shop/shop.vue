<template>
 <div id="shopContent">
   <header>
     <div class="shopContent">
       <div class="top">
         <div class="center">
           <span class="car">购物车</span>
           <span class="coupon">领券</span>
         </div>
       </div>
       <div class="down">
         <div class="sort">
           <span>30天无忧退货</span>
           <span>48小时快速退款</span>
           <span>满88元免邮</span>
         </div>
       </div>
     </div>
   </header>
   <div class="defaultPage">
     <div class="container">
       <div class="defaulImg"></div>
       <div class="txt">
         <div class="text"><span>去添加点东西吧</span></div>
         <button @click="$router.replace('/person')">登录</button>
       </div>
     </div>
   </div>
 </div>
</template>

<script type="text/ecmascript-6">
  export default {
    name: ""
  }
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>
  #shopContent
    width 750px
    height 100%
    background-color #f4f4f4
    margin-bottom 100px
    header
      height 356px
      width 750px
      .shopContent
        width 100%
        height 158px
        padding-bottom 198px
        .top
          width 750px
          height 88px
          background-color #fff
          .center
            width 690px
            height 88px
            padding 0px 30px
            line-height 88px
            .car
              font-size 40px
            .coupon
              color #B4282D
              font-size 32px
              float right


        .down
          width 750px
          height 70px
          .sort
            width 690px
            height 70px
            padding 0px 30px
            display flex
            justify-content space-around
            line-height 70px
            color #666
            font-size 26px


    .defaultPage
      position fixed
      top 0px
      width 100%
      .container
        width 100%
        height 300px
        margin 498px auto
        .defaulImg
          display inline-block
          width 100%
          height 248px
          margin-bottom 8px
          background-image url("//yanxuan-static.nosdn.127.net/hxm/yanxuan-wap/p/20161201/style/img/icon-normal/noCart-d6193bd6e4.png")
          background-repeat no-repeat
          background-position center center

        .txt
          width 100%
          height 169px
          text-align center
          .text
            margin-bottom 50px
            width 100%
            height 27px
            color #999
          button
            width 480px
            height 92px
            margin 0px 135px
            background-color #b4282d
            font-size 34px
</style>
