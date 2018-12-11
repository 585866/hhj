
<template>
  <div>
    <HomeHeader></HomeHeader>
    <HomeSwiper :list="swiperList"></HomeSwiper>
    <HomeIcon :list="iconList"></HomeIcon>
    <HomeRecommend :list="recommendList"></HomeRecommend>
    <HomeWeekend :list="weekendList"></HomeWeekend>
  </div>
</template>

<script>
  import HomeHeader from '../home/components/Header'
  import HomeSwiper from './components/Swiper'
  import HomeIcon from './components/Icons'
  import HomeRecommend from './components/Recommend'
  import HomeWeekend from './components/Weekend'
  import axios from  'axios'
  import { mapState } from 'vuex'
    export default {
        name: "Home",
      data(){
          return{
            swiperList: [],
            iconList: [],
            recommendList: [],
            weekendList: [],
          }
      },
      computed: {
        ...mapState(['city'])
      },
      components:{
          HomeHeader,
          HomeSwiper,
          HomeIcon,
          HomeRecommend,
          HomeWeekend
      },
      methods:{
          getHomeInfo(){
            axios.get('/api/index.json?city='+this.city).then(this.getHomeInfoSucc)
          },
          getHomeInfoSucc(res){
            res=res.data;
            if(res.ret && res.data){
              const data=res.data;
              this.swiperList = data.swiperList;
              this.iconList = data.iconList;
              this.recommendList = data.recommendList;
              this.weekendList = data.weekendList
            }
          },
      },
      mounted(){
        this.lastCity = this.city
        this.getHomeInfo()
      },
      activated () {
        if (this.lastCity !== this.city) {
          this.lastCity = this.city
          this.getHomeInfo()
        }
      }
    }
</script>

<style lang="stylus" scoped>
</style>
