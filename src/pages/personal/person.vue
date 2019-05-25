<template>
  <div class="personalContent">
    <div class="t_header">
      <i class="t_home"  @click="$router.replace('/home')"></i>
      <div class="t_header_text">

      </div>
      <div>
        <i class="t_search"></i>
        <i class="t_cart"></i>
      </div>
    </div>
    <div class="p_content" v-show="!showPhone">
      <div class="p_header">
        <div class="p_logo">
          <img src="//yanxuan.nosdn.127.net/bd139d2c42205f749cd4ab78fa3d6c60.png" alt="">
        </div>
        <div class="person_btn">
          <mt-button type="default"size="large" class="btn_phone" @click="showPhone=!showPhone">
            <i class="iconfont icon-shouji"></i>
            手机号登录
          </mt-button>
          <mt-button type="default"size="large" class="btn_sns">
            <i class="iconfont icon-youxiang1"></i>
            邮箱账号登录
          </mt-button>
          <p>手机号快速注册<i class="iconfont icon-arrow-right"></i></p>
        </div>
      </div>
      <div class="p_bottom">
        <div><i class="iconfont icon-weixin"></i>微信</div>
        <div><i class="iconfont icon-qq"></i>QQ</div>
        <div><i class="iconfont icon-weibo"></i>微博</div>
      </div>
    </div>
    <div class="p_hide" v-show="showPhone">
      <div class="hide_logo">
        <img src="//yanxuan.nosdn.127.net/bd139d2c42205f749cd4ab78fa3d6c60.png" alt="">
      </div>
      <div class="hide_code">
        <form>
          <div class="hide_txt">
            <input type="text" placeholder="请输入手机号" maxlength="11" v-validate="{required: true, regex: /^1\d{10}$/}">
            <span style="color: red;">{{errors.first('phone')}}</span>
          </div>
          <div class="hide_txt btn">
            <input type="text" placeholder="请输入短信验证码" v-validate="{required: true, regex: /^\d{6}$/}">
            <span style="color: red;">{{errors.first('code')}}</span>
            <button :disabled= "Maximum>0" class="gain" @click.prevent="handleGain">{{Maximum > 0 ? `已发送(${Maximum}s)`:'获取验证码'}}</button>
          </div>
          <div class="hide_matter">
            <a href="https://aq.reg.163.com/ydaq/offline">遇到问题？</a>
            <a href="javascript:;" style="color: #333">使用密码验证登录</a>
          </div>
          <mt-button size="large" type="default" class="hide_large">登录</mt-button>
          <mt-button size="large" type="default" class="hide_large red">其他登录方式</mt-button>
          <div class="registe">
            <a href="javascript:;">注册账号  ></a>
          </div>

        </form>
      </div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">

  export default {
    name: "personal",
    data(){
      return{
        Maximum:0,//倒计时
        gain:true,//验证码状态
        showPhone:false//手机号登录转态
      }
    },
    methods:{
      handleGain(){
        console.log('00000');
        this.Maximum=30

        const InvalId = setInterval(()=>{
          this.Maximum--
          if(this.Maximum===0){
            clearInterval(InvalId)
          }
        },1000)
      }
    }

  }
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>
  .personalContent
    width 100%
    height 100%
    background-color #f4f4f4
    .t_header
      z-index 2
      background-color #fff
      width 100%
      height 100px
      box-sizing border-box
      padding 0 24px
      display flex
      align-items center
      justify-content space-between
      .t_home
        width 46px
        height 46px
        background-image url("http://yanxuan-static.nosdn.127.net/hxm/yanxuan-wap/p/20161201/style/img/sprites/tabBar-s43a0dc8a7d-de25ef8e19.png")
        background-repeat no-repeat
        background-size 53px 660px
        background-position -1px -340px
      .t_header_text
        width 320px
        height 100px
        line-height 100px
        background-image url("http://yanxuan-static.nosdn.127.net/hxm/yanxuan-wap/p/20161201/style/img/icon-normal/indexLogo-a90bdaae6b.png")
        background-repeat no-repeat
        background-position center
        background-size 50%
      >div
        width 140px
        height 100px
        display flex
        justify-content space-between
        .t_search
          width 62px
          height 100px
          background-image url("http://yanxuan-static.nosdn.127.net/hxm/yanxuan-wap/p/20161201/style/img/icon-normal/search2-553dba3aff.png")
          background-repeat no-repeat
          background-size 35px 50px
          background-position 12px 24px
        .t_cart
          width 49px
          height 100px
          background-image url("http://yanxuan-static.nosdn.127.net/hxm/yanxuan-wap/p/20161201/style/img/sprites/tabBar-s43a0dc8a7d-de25ef8e19.png")
          background-repeat no-repeat
          background-size 53px 780px
          background-position -1px -63px
    .p_content
      width 100%
      height 1200px
      position relative
      .p_header
        width 100%
        height auto
        .p_logo
          width 100%
          height 88px
          padding 160px 0 160px 0
          text-align center
          img
            width 40%
            height 80%


        .person_btn
          width 90%
          height 292px
          padding 0px 20px 0px 20px
          margin-bottom 205px
          font-size 30px
          margin 0 auto
          .btn_phone
            height 88px
            font-size 30px
            border 1px solid #b4282d
            background-color #b4282d
            color #fff
            margin-bottom 32px
            vertical-align middle
            i
              font-size 48px
              vertical-align middle
          .btn_sns
            line-height 88px
            height 88px
            font-size 30px
            border 1px solid #b4282d
            margin-bottom 32px
            vertical-align middle
            i
              font-size 44px
              vertical-align middle
          p
            text-align center
            i
              font-size 28px



      .p_bottom
        width 100%
        height 42px
        position absolute
        bottom 20px
        left 0px
        display flex
        justify-content center
        text-align center
        font-size 30px
        color #999
        div
          width 100px
          height 40px
          padding 0px 40px 0 40px
          border-right 1px solid black
        &.last-child
          border-right none
        i
          color #999
          font-size 32px

    .p_hide
      width 100%
      height 1200px
      position relative
      background-color #fff
      padding-top 10px
      .hide_logo
        width 100%
        height 100px
        margin-top 40px
        text-align center
        img
          width 30%
          height 60%
      .hide_code
        width 100%
        height 100%
        margin 25px  auto 0px
        form
          width 90%
          height 1200px
          padding 0px 40px 0 40px
          margin 60px auto 0
          .hide_txt
            width 90%
            border-bottom 1px solid #999
            height 90px
            margin-top 30px
            input
              outline none
              width 100%
              height 100%
              &::-webkit-input-placeholder
                font-size 30px
            span
              height 20px
              display line-height
              width 100%
          .btn
            position relative
            .gain
              width 155px
              height 60px
              text-align center
              line-height 60px
              position absolute
              right 0px
              bottom 6px
              font-size 26px
              background-color rgba(255,255,255,.3)
              border 1px solid #999
              border-radius 10px
          .hide_matter
            margin-top 40px
            width 100%
            height 80px
            display flex
            justify-content space-between
            font-size 28px

          .hide_large
            width 100%
            height 90px
            background-color #b4282d
            color #fff
            font-size 30px
            margin-bottom 30px
            border 1px solid #b4282d
            border-radius 10px
            &.red
              background-color #fff
              color #b4282d
          .registe
            width 100%
            height 40px
            line-height 40px
            font-size 30px
            color #333
            text-align center

</style>
