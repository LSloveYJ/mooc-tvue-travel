<template>
  <div>
    <div class="title">
      {{recommend.title}}
    </div>
    <ul>
      <li class="item border-bottom" v-for="item in recommend.items" :key="item.id">
        <img class="item-img" :src="item.src"/>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: 'Recommend',
    props: ['recommend'],
  };
</script>

<style lang="stylus" scoped>
  @import '~style/mixins.styl'
  .title
    margin-top .2rem
    line-height .8rem
    background #eee
    text-indent .2rem

  .item
    display: flex
    height 1.9rem

    .item-img
      width 1.7rem
      height 1.7rem
      padding .1rem

    .item-info
      flex 1
      padding .1rem
      min-width 0

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
