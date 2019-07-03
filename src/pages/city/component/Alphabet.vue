<template>
  <ul class="list">
    <li class="item"
        v-for="item of letters"
        :key="item"
        @click="chooseAlphabet(item)"
        @touchstart="handleTouchStart"
        @touchmove="handleTouchMove"
        @touchend="handleTouchEnd"
        :ref="item"
    >
      {{item}}
    </li>
  </ul>
</template>

<script>
  export default {
    name: 'Alphabet',
    props: ['cities'],
    data() {
      return {
        touchStatus: false,
      };
    },
    computed: {
      letters() {
        const alphabet = [];
        Object.keys(this.cities)
          .forEach(key =>
            alphabet.push(key),
          );
        return alphabet;
      },
    },
    methods: {
      chooseAlphabet(item) {
        this.$emit('toChooseAlphabet', item);
      },
      handleTouchStart() {
        this.touchStatus = true;
      },
      handleTouchMove(e) {
        if (this.touchStatus) {
          const startY = this.$refs.A[0].offsetTop;
          const touchY = e.touches[0].clientY - 81;
          const index = Math.floor((touchY - startY) / 20);
          if (index >= 0 && index < this.letters.length) {
            this.$emit('toChooseAlphabet', this.letters[index]);
          }
        }
      },
      handleTouchEnd() {
        this.touchStatus = false;
      },
    },
  };
</script>


<style lang="stylus" scoped>

  @import '~style/varibles.styl'

  .list
    display flex
    flex-direction column
    justify-content center
    position absolute
    top 1.58rem
    right 0
    bottom 0
    width .4rem

    .item
      text-align center
      line-height .4rem
      color #25a4bb
</style>
