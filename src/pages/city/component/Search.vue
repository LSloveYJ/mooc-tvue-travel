<template>
  <div class="search">
    <input type="text" class="search-input" placeholder="城市名或拼音（如北京/beijing）">
  </div>
</template>

<script>
  export default {
    name: 'Search',
  };
</script>

<style lang="stylus" scoped>
  @import '~style/varibles.styl'

  .search
    height .72rem
    background $headerBgColor
    padding 0 .1rem

    .search-input
      box-sizing border-box
      height .62rem
      width 100%
      line-height .62rem
      padding 0 .1rem
      text-align center
      color #666
      border-radius .06rem


</style>
