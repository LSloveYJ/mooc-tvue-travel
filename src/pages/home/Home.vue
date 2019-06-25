<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons :iconList="iconList"></home-icons>
    <home-recommend :recommend="recommend"></home-recommend>
    <home-weekend :weekend="weekend"></home-weekend>
  </div>
</template>


<script>
  import axios from 'axios';
  import HomeHeader from './components/Header';
  import HomeSwiper from './components/Swiper';
  import HomeIcons from './components/Icons';
  import HomeRecommend from './components/Recommend';
  import HomeWeekend from './components/Weekend';

  export default {
    components: {
      HomeHeader,
      HomeSwiper,
      HomeIcons,
      HomeRecommend,
      HomeWeekend,
    },
    data() {
      return {
        weekend: '',
        recommend: '',
        iconList: '',
      };
    },
    created() {
      this.getHomeInfo();
    },
    methods: {
      getHomeInfo() {
        axios.get('/api/index.json')
          .then(this.getHomeInfoSucc);
      },
      getHomeInfoSucc(res) {
        this.weekend = res.data.weekend;
        this.recommend = res.data.recommend;
        this.iconList = res.data.iconList;
      },
    },
  };
</script>
