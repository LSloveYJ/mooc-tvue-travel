<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list
      :cities="cities"
      :hotCities="hotCities"
      :chooseAlphabet="chooseAlphabet"
    ></city-list>
    <alphabet :cities="cities" @toChooseAlphabet="toChooseAlphabet"></alphabet>
  </div>
</template>

<script>
  import axios from 'axios';
  import CityHeader from './component/Header';
  import CitySearch from './component/Search';
  import CityList from './component/List';
  import Alphabet from './component/Alphabet';

  export default {
    name: 'City',
    data() {
      return {
        cities: {},
        hotCities: {},
        chooseAlphabet: '',
      };
    },
    components: {
      CityHeader,
      CitySearch,
      CityList,
      Alphabet,
    },
    mounted() {
      this.getCityInfo();
    },
    methods: {
      getCityInfo() {
        axios.get('/api/city.json')
          .then(this.getCityInfoSucc);
      },
      getCityInfoSucc(res) {
        const response = res.data;
        if (response && response.ret) {
          this.cities = response.data.cities;
          this.hotCities = response.data.hotCities;
        }
      },
      toChooseAlphabet(index) {
        this.chooseAlphabet = index;
      },
    },
  };
</script>

<style scoped>

</style>
