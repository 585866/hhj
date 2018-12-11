<template>
  <div class="header">
    <router-link tag="div" to="/" class="header-back">
      <div class="iconfont icon-fanhui"></div>
    </router-link>
    <img class="backgroundUrl" src="https://s.qunarzz.com/usercenter_mobile/images/my/mybgnew-20161111.jpg" alt="">
    <img alt="" class="my-avatar-img" src="https://source.qunarzz.com/usercenter/touch/avatar.png">
    <div class="user">
      <div class="login">登录/</div>
      <span></span>
      <div class="resign">注册</div>
    </div>
  </div>
</template>

<script>
    export default {
        name: "UserHeader"
    }
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    position:relative
    .header-back
      position: absolute
      left: .2rem
      top: 0
      width: .8rem
      height: .8rem
      line-height: .8rem
      text-align: center
      .header-abs-back
        color: #fff
        font-size: .4rem
    .backgroundUrl
      width: 100%
      height:3.5rem;
    .my-avatar-img
      position:absolute
      top:45px
      left:41%
      width:1.5rem
      height:1.5rem
      box-shadow: 0 0.03rem 0.03rem rgba(0,0,0,0.05);
      border:3px solid rgba(250,250,250,0.5)
      border-radius: 100%;
    .user
      position:absolute
      top:135px
      left:41%
      .login,.resign
        color: #ffffff
        font-size:20px
        float:left

</style>
