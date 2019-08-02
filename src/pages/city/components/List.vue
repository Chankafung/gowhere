<template lang="html">
  <div>
    <div class="list" ref="wrapper">
      <div class="content">
        <div class="area">
          <div class="title">当前城市</div>
          <div class="button-now">南京</div>
        </div>
        <div class="area">
          <div class="title">热门城市</div>
          <ul class="button-list">
            <li v-for="item of hotCities" :key="item.id">{{item.name}}</li>
          </ul>
        </div>
        <div class="area" v-for="(item, key, index) in cities" :key="index" :ref="key">
          <div class="title">{{key}}</div>
          <ul class="button-list">
            <li v-for="city of item" :key="city.id">{{city.name}}</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    cities: Object,
    hotCities: Array,
    letter: String
  },
  data () {
    return {

    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .list
    position: absolute
    top: .88rem
    left: 0
    right: 0
    bottom: 0
    overflow: hidden
    .title
      background-color: #f5f5f5
      font-size: .24rem
      padding: .24rem .3rem
    .button-now
      height: .9rem
      line-height: .9rem
      padding-left: .2rem
    .button-list
      background-color: #fff
      overflow: hidden
      position: relative
      &::before
        content:''
        width: 33.33%
        height: 100%
        position: absolute
        left: 33.33%
        top: 0
        border-left: .02rem solid #ddd
        border-right: .02rem solid #ddd
      li
        width: 33.33%
        height: .9rem
        line-height: .9rem
        border-bottom: .02rem solid #ddd
        text-align: center
        float: left
        margin-bottom: -1px
        position: relative
        z-index: 10
        ellipsis()
</style>
