<template>
  <div>
    <div class="title">
      {{weekend.title}}
    </div>
    <ul>
      <li class="item border-bottom" v-for="item in weekend.items" :key="item.id">
        <div class="item-img-cotent">
          <img class="item-img" :src="item.src"/>
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: 'Weekend',
    props: ['weekend'],
  };
</script>

<style lang="stylus" scoped>
  @import '~style/mixins.styl'
  .title
    line-height .8rem
    background #eee
    text-indent .2rem

  .item-img-cotent
    overflow hidden
    height 0
    padding-bottom 25.6%

    .item-img
      width 100%

  .item-info
    padding .1rem

    .item-title
      margin-top .1rem
      line-height .54rem
      font-size .32rem
      ellipsis()

    .item-desc
      line-height .4rem
      color #ccc
      ellipsis()

    .item-button
      line-height .44rem
      background #ff9300
      margin-top .16rem
      border-radius .06rem
      color #fff
      text-align center
      padding 0 .2rem


</style>
