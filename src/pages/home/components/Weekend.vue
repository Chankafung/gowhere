<template lang="html">
  <div>
    <div class="weekend-title">周末去哪儿</div>
    <div class="weekend-wrapper" v-for="item in weekendList" :key="item.id">
      <div class="weekend-img">
        <img :src="item.imgUrl" alt="">
      </div>
      <p class="weekend-titletxt">{{item.title}}</p>
      <p class="weekend-desc">{{item.desc}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props: {
    weekendList: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .weekend-title
    height: .8rem
    padding-left: .26rem
    line-height: .8rem
    color: #212121
    background-color: #f5f5f5
  .weekend-wrapper
    margin-bottom: .1rem
    background: #fff
    .weekend-img
      overflow: hidden
      height: 0
      padding-bottom: 37%
      img
        width: 100%
    .weekend-titletxt
      overflow: hidden
      color: #212121
      font-size: .28rem
      line-height: .48rem
      padding-left: .2rem
      margin-top: .14rem
      ellipsis()
    .weekend-desc
      overflow: hidden
      color: #616161
      font-size: .24rem
      line-height: .42rem
      padding-left: .2rem
      padding-bottom: .2rem
      ellipsis()
</style>
