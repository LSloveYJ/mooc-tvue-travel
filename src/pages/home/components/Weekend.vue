<template>
  <div>
    <div class="title">
      {{title}}
    </div>
    <ul>
      <li class="item border-bottom" v-for="item in items" :key="item.id">
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
    data() {
      return {
        title: '周末去哪儿',
        items: [
          {
            id: 1,
            src: 'https://source.qunarzz.com/site/images/wns/20190621_qunar_dujia_homepage_2.jpg',
            title: '国际旅游',
            desc: '天天实惠,天天实惠,天天实惠',
          }, {
            id: 2,
            src: 'https://source.qunarzz.com/site/images/wns/20190621_dujia_homepage_top_banner_5.jpg',
            title: '海岛旅游',
            desc: '天天实惠,天天实惠,天天实惠',
          }, {
            id: 3,
            src: 'https://source.qunarzz.com/site/images/wns/2019621_dujia_homepage_top_banner_5.jpg',
            title: '兵马俑旅游',
            desc: '天天实惠,天天实惠,天天实惠',
          }, {
            id: 4,
            src: 'https://source.qunarzz.com/site/images/wns/20190620_qunar_dujia_homepage_3.jpg',
            title: '日本双飞旅游',
            desc: '天天实惠,天天实惠,天天实惠',
          }, {
            id: 5,
            src: 'https://source.qunarzz.com/site/images/wns/20190621_dujia_homepage_top_banner_5.jpg',
            title: '日本双飞旅游',
            desc: '天天实惠,天天实惠,天天实惠',
          }, {
            id: 6,
            src: 'https://source.qunarzz.com/site/images/wns/20190531_dujia_homepage_top_banner_4.jpg',
            title: '日本双飞旅游',
            desc: '天天实惠,天天实惠,天天实惠',
          },
        ],
      };
    },
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
