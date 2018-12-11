
<template>
  <div id="app">
    <keep-alive>
      <router-view></router-view>
    </keep-alive>
      <div class="tab">
        <div class="tab-item">
          <router-link tag="div" to="/">
            <i class="iconfont icon-index"></i><span class="name">首&nbsp;&nbsp;页</span>
          </router-link>
        </div>
        <div class="tab-item">
          <router-link tag="div" to="/">
            <i class="iconfont icon-xiangqing"></i><span class="name">热&nbsp;&nbsp;门</span>
          </router-link>
        </div>
        <div class="tab-item">
          <router-link tag="div" to="/user">
            <i class="iconfont icon-user-circle-o"></i><span class="name">我&nbsp;&nbsp;的</span>
          </router-link>
        </div>
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="stylus" scoped>
 .tab
   position:fixed
   bottom:0
   z-index:999
   height:60px
   width: 100%
   background:#eee
   border-bottom :1px solid #eee
   line-height:50px
   .tab-item
      float:left
      width:33.33%
      text-align :center
      cursor:pointer
      position:relative
      .name
        display inline-block
        position:absolute
        top:22px
        left:52px

</style>
