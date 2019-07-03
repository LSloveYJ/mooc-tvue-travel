<template>
  <div class="list" ref="wrapper">
    <div>
      <div>
        <div class="area">
          <div class="title border-topbottom">当前城市</div>
          <div class="button-list">
            <div class="button-wrapper">
              <div class="button">
                <div>西安</div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div>
        <div class="area">
          <div class="title border-topbottom">热门城市</div>
          <div class="button-list">
            <div class="button-wrapper" v-for="item of hotCities" :key="item.id">
              <div class="button">
                <div>{{item.name}}</div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div>
        <div class="area"
             v-for="(items,key) of cities"
             :key="key">
          <div class="title border-topbottom"
               :ref="key">
            {{key}}
          </div>
          <div class="item-list"
               v-for="item of items"
               :key="item.id">
            <div class="item border-bottom">{{item.name}}</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import BScroll from 'better-scroll';

  export default {
    name: 'List',
    props: ['cities', 'hotCities', 'chooseAlphabet'],
    mounted() {
      this.scroll = new BScroll(this.$refs.wrapper);
    },
    watch: {
      chooseAlphabet() {
        const alphabet = this.chooseAlphabet;
        if (alphabet) {
          this.scroll.scrollToElement(this.$refs[alphabet][0]);
        }
      },
    },
  };
</script>

<style lang="stylus" scoped>

  .list
    position absolute
    top 1.58rem
    right 0
    bottom 0
    left 0
    overflow hidden

  .title
    line-height .54rem
    background #eee
    padding-left .2rem
    color #666
    font-size .26rem

  .button-list
    padding .1rem .6rem .1rem .1rem
    overflow hidden

    .button-wrapper
      float left
      width 33.33%

      .button
        margin .1rem
        padding .1rem 0
        text-align center
        border .02rem solid #ccc
        border-radius .06rem

  .item-list
    .item
      line-height .76rem
      padding-left .2rem


  .border-topbottom
  &:before
    border-color #ccc

  &:after
    border-color #ccc

  .border-bottom
  &:before
    border-color #ccc


</style>
