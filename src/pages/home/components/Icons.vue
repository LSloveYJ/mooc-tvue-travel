<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon" v-for="item in page " :key="item.id">
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
    props: ['iconList'],
    data() {
      return {
        swiperOption: {
          pagination: {
            el: '.swiper-pagination',
          },
        },
      };
    },
    computed: {
      pages() {
        const pages = [];
        // 先是0  后是9
        if (this.iconList.length) {
          this.iconList.forEach((item, index) => {
            const page = Math.floor(index / 8);
            if (!pages[page]) {
              pages[page] = [];
            }
            pages[page].push(item);
          });
        }
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
