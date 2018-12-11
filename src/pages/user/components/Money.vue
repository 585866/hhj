<template>
    <div class="list">
      <div class="item-qianbao">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#icon-qianbao"></use>
        </svg>
        <span class="name">我的钱包</span>
      </div>
      <ul class="item-money">
        <li class="m-item" v-for="(item) in itemList"><span class="num">{{item.num}}</span>{{item.title}}</li>
      </ul>
    </div>
</template>

<script>
    export default {
        name: "UserMoney",
      data(){
          return{
            itemList:[
              {
                num:"0.00",
                title:"账户余额"
              },
              {
                num:0,
                title:"星券"
              },
              {
                num:"0张",
                title:"银行卡"
              }
            ]
          }
      }
    }
</script>

<style lang="stylus" scoped>
  .list
    padding:0.2rem 0
    background:#eee
    .item-qianbao
      padding:0 0.2rem
      background:#fff
      height:.85rem
      line-height:.85rem
      display:flex
      .icon
        width: 0.5rem
        height: 0.5rem;
        fill: currentColor;
        overflow: hidden;
        margin-top:.16rem
      .name
        font-size:.3rem
        font-weight:700
        flex:1
        padding-left:.3rem
    .item-money
      background:#fff
      height:1.2rem
      width:100%
      display :flex
      line-height:1.2rem
      padding-top:.6rem
      .m-item
        flex:1
        text-align :center
        position:relative
        font-size:18px
        color:#999999
      .num
        position:absolute
        top:-.65rem
        left:0.88rem
        text-align :center
        width:33.333%
        font-size:16px
        color:#000
</style>
