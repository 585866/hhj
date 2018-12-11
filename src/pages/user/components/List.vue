<template>
    <div class="list">
      <li class="list-item" v-for="item in iconList">
        <svg class="icon" aria-hidden="true">
          <use :xlink:href="item.iconUrl"></use>
        </svg>
        <span class="name">{{item.name}}</span>
        <i class="iconfont icon-qianjin"></i>
      </li>
    </div>
</template>

<script>
    export default {
        name: "UserList",
      data(){
          return{
            iconList:[
              {
                name:'我的订单',
                iconUrl:'#icon-dingdan'
              },
              {
                name:'我的退款',
                iconUrl:'#icon-tuikuan'
              },
              {
                name:'我的发票',
                iconUrl:'#icon-fapiao'
              },
              {
                name:'我的攻略',
                iconUrl:'#icon-gonglie'
              }
            ]
          }
      }
    }
</script>

<style lang="stylus" scoped>
.list
  .list-item
    list-style :none
    height:.85rem
    padding:0 0.2rem
    line-height:.85rem
    display:flex
    .icon
      width: 0.5rem
      height: 0.5rem;
      fill: currentColor;
      overflow: hidden;
      margin-top:.16rem
    .name
      flex:1
      padding:0 .4rem
      font-size:.3rem
      font-weight:700

</style>
