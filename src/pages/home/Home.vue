<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons></home-icons>
    <home-recommend></home-recommend>
    <home-weekend></home-weekend>
    {{getHomeInfo()}}
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
    methods: {
      getHomeInfo() {
        axios.get('/api/index.json')
          .then(this.getHomeInfoSucc);
      },
      getHomeInfoSucc(res) {
        console.log(res);
      },
    },
  };
</script>
