<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont">&#xe624;</span>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{city}}
        <span class="iconfont">&#xe6aa;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    display: flex
    line-height: .86rem
    background: $bgColor
    color: #fff
    .header-left
      width: .64rem
      float: left
      text-align: center
      span.iconfont
        font-size: .4rem
    .header-input
      flex: 1
      height: .64rem
      margin-left: .2rem
      margin-top: .12rem
      background: #fff
      border-radius: .1rem
      color: #ccc
      line-height: .64rem
      padding-left: .2rem
    .header-right
      padding: 0 .22rem
      float: height
      text-align: center
      color: #fff
      span.iconfont
        margin-left: -.04rem
</style>
