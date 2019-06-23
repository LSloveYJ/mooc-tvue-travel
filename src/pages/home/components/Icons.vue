<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon" v-for="item in page" :key="item.id">
          <div class="icon-img">
            <img
              class="icon-img-content"
              :src="item.path">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
  export default {
    name: 'Icon',
    data() {
      return {
        swiperOption: {
          pagination: {
            el: '.swiper-pagination',
          },
        },
        iconList: [
          {
            id: 1,
            path: 'https://imgs.qunarzz.com/vc/fd/55/94/6c7152c2a8b35a9c49bb26ea25.png_92.png',
            desc: '热门景点热门景点热门景点热门景点',
          }, {
            id: 2,
            path: 'https://imgs.qunarzz.com/vc/eb/d9/1b/e24bca3f1ef6ae6ebdee15e4ca.png_92.png',
            desc: '周边游',
          }, {
            id: 3,
            path: 'https://imgs.qunarzz.com/vc/c8/01/32/8f6e29b7b6ce0a807742c2587a.png_92.png',
            desc: '出境游',
          }, {
            id: 4,
            path: 'https://imgs.qunarzz.com/vc/c3/f2/54/2e1c8f9403de1ed28895c9ffa4.png_92.png',
            desc: '国内游',
          }, {
            id: 5,
            path: 'https://imgs.qunarzz.com/vc/68/4a/91/b7f09964d1e7a6280cca361c46.png_92.png',
            desc: '一日游',
          }, {
            id: 6,
            path: 'https://imgs.qunarzz.com/vc/77/21/6b/64a35f4ab3ab1fad57731edb3d.png_92.png',
            desc: '签证',
          }, {
            id: 7,
            path: 'https://imgs.qunarzz.com/vc/68/4a/91/b7f09964d1e7a6280cca361c46.png_92.png',
            desc: '主题游',
          }, {
            id: 8,
            path: 'https://imgs.qunarzz.com/vc/c8/01/32/8f6e29b7b6ce0a807742c2587a.png_92.png',
            desc: '潜水',
          }, {
            id: 9,
            path: 'https://imgs.qunarzz.com/vc/c8/01/32/8f6e29b7b6ce0a807742c2587a.png_92.png',
            desc: '潜水',
          },
        ],
      };
    },
    computed: {
      pages() {
        const pages = [];
        this.iconList.forEach((item, index) => {
          const page = Math.floor(index / 8);
          if (!pages[page]) {
            pages[page] = [];
          }
          pages[page].push(item);
        });
        return pages;
      },
    },
  };
</script>

<style lang="stylus" scoped>
  @import '~style/varibles.styl'
  @import '~style/mixins.styl'
  .icons >>> .swiper-container
    height 0
    padding-bottom 50%

  .icons
    margin-top .2rem
    .icon
      position relative
      overflow hidden
      float left
      width 25%
      height 0
      padding-bottom 25%

      .icon-img
        position absolute
        top 0
        left 0
        right 0
        bottom .44rem
        box-sizing border-box
        padding .1rem

        .icon-img-content
          display block
          margin 0 auto
          height 100%

      .icon-desc
        position absolute
        left 0
        right 0
        bottom 0
        line-height .44rem
        color $iconColor
        text-align center
        ellipsis()

</style>
