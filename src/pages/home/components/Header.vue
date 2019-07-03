<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe600;</div>
    </div>
    <div class="header-input">
      <span class="iconfont search-icon">&#xe61a;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        城市
        <span class="iconfont arrow-icon">&#xe654;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
  export default {
    name: 'HomeHeader',
  };
</script>
<style lang="stylus" scoped>
  @import '~style/varibles.styl'
  .header
    display: flex
    background: $headerBgColor
    line-height: .86rem
    color: #fff

    .header-left
      width: .64rem
      float: left

      .back-icon
        text-align: center
        font-size: .4rem

    .header-input
      flex: 1
      background: #ffffff
      line-height: .64rem
      margin: .12rem .12rem .12rem
      color: #cacaca
      border-radius: .1rem

      .search-icon
        margin-left: .2rem

    .header-right
      width: 1.24rem
      text-align: center
      color white

      .arrow-icon
        margin-left: -.04rem
        font-size: .24rem
</style>

