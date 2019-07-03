<template>
  <div class="city-header">
    <router-link to="/">
      <div class="iconfont city-back-icon">&#xe600;</div>
    </router-link>
    城市选择
  </div>
</template>

<script>
  export default {
    name: 'Headers',
  };
</script>

<style lang="stylus" scoped>
  @import '~style/varibles.styl'
  .city-header
    position relative
    overflow hidden
    height $height
    background: $headerBgColor
    line-height: $height
    color #ffffff
    text-align center
    font-size .32rem

    .city-back-icon
      position absolute
      top 0
      left 0
      width .64rem
      color #ffffff
      text-align: center
      font-size: .4rem

</style>
