<template>
  <div>
    <div class="title">
      热销推荐
    </div>
    <ul>
      <li class="item border-bottom" v-for="item in items" :key="item.id">
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
    data() {
      return {
        items: [
          {
            id: 1,
            src: 'http://img1.qunarzz.com/sight/p0/1507/36/ce3d2d6c9ab44d67ae68d940b8781829.water.jpg_250x250_b8d94d62.jpg',
            title: '国际旅游',
            desc: '天天实惠,天天实惠,天天实惠',
          }, {
            id: 2,
            src: 'http://img1.qunarzz.com/sight/p0/1505/f5/f5f45e1a83537bcb.water.jpg_250x250_63e3520a.jpg',
            title: '海岛旅游',
            desc: '天天实惠,天天实惠,天天实惠',
          }, {
            id: 3,
            src: 'http://img1.qunarzz.com/sight/p0/1604/78/78873494f26e554090.water.jpg_250x250_0565d534.jpg',
            title: '兵马俑旅游',
            desc: '天天实惠,天天实惠,天天实惠',
          }, {
            id: 4,
            src: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
            title: '日本双飞旅游',
            desc: '天天实惠,天天实惠,天天实惠',
          }, {
            id: 5,
            src: 'http://img1.qunarzz.com/sight/p0/201308/08/41150dacc0e3a0c8c8d65eac.jpg_200x200_c62292e9.jpg',
            title: '日本双飞旅游',
            desc: '天天实惠,天天实惠,天天实惠',
          }, {
            id: 6,
            src: 'http://img1.qunarzz.com/sight/p0/1508/89/895a1b7add84f23faca053ce9e3153db.water.jpg_200x200_99ae30ee.jpg',
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
        padding 0  .2rem


</style>
