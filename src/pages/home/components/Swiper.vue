<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img"
             :src="item.img"/>
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
  export default {
    name: 'homeSwiper',
    data() {
      return {
        swiperOption: {
          pagination: {
            el: '.swiper-pagination',
          },
          loop: true,
        },
        swiperList: [{
          id: 1,
          img: 'http://source.qunarzz.com/site/images/wns/20190621_dujia_homepage_top_banner_5.jpg',
        }, {
          id: 2,
          img: 'http://source.qunarzz.com/site/images/wns/20190621_qunar_dujia_homepage_2.jpg',
        }],
      };
    },
  };
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #ffffff

  .wrapper
    overflow hidden
    width 100%
    height 0
    padding-bottom 25.6%
    background: #cacaca

    .swiper-img
      width: 100%


</style>
