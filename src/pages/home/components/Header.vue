<template>
  <div>
    <div class="header">
      <div class="header-left">
        <div class="iconfont"></div>
      </div>
      <div class="header-input">
        <span class="iconfont">&#xe632;</span>
        输入城市/景点/游玩主题
      </div>
      <router-link to="/city">
        <div class="header-right">{{this.city}}
          <span class="iconfont arrow-icon">&#xe64a;</span>
        </div>
      </router-link>
    </div>
    <div class="backgroundColor" :style="opacityStyle"  v-show="!showBar"></div>
  </div>
</template>

<script>
  import{mapState} from 'vuex'
    export default {
        name: "HomeHeader",
      data(){
          return{
            showBar:true,
            opacityStyle: {
              opacity: 0
            }
          }
      },
      computed: {
        ...mapState(['city'])
      },
      methods: {
        handleScroll () {
          const top = document.documentElement.scrollTop
          if (top > 60) {
            let opacity = top / 140
            opacity = opacity > 1 ? 1 : opacity
            this.opacityStyle = { opacity }
            this.showBar = false
          } else {
            this.showBar = true
          }
        }
      },
      mounted () {
        window.addEventListener('scroll', this.handleScroll)
      },
      unmounted () {
        window.removeEventListener('scroll', this.handleScroll)
      }
    }
</script>

<style lang="stylus" scoped>
  @import '../../../assets/styles/varibles.styl'
  .header
    position:fixed
    line-height:$headerHeight
    background: transparent
    color:#fff
    z-index:999
    display:flex
    top:0
    width:100%
    .header-left
      width:.64rem
      float:left
      opacity :1
      .back-icon
        text-align: center
        font-size: .4rem
    .header-input
      flex: 1
      height: .60rem
      line-height: .60rem
      margin: .1rem
      margin-left: .2rem
      padding-left: .2rem
      background: #fff
      border-radius: 0.5rem
      color: #ccc
      opacity :1
    .header-right
      min-width:1.24rem
      float:right
      text-align :center
      color:#fff
      .arrow-icon
        margin-left: -.04rem
        font-size: .24rem
  .backgroundColor
    position:fixed
    line-height:$headerHeight
    background: #00bcd4
    z-index:998
    top:0
    width:100%
    height:43px
</style>
