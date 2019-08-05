<template lang="html">
  <div>
      <div class="header">
        <router-link to="/">
          <span class="iconfont">&#xe624;</span>
        </router-link>
        城市选择
      </div>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  .header
    height: .88rem
    line-height: .88rem
    text-align: center
    overflow: hidden
    background-color: #00bcd4
    color: #fff
    font-size: .32rem
    position: relative
    .iconfont
      color: #fff
      position: absolute
      width: .8rem
      height: .88rem
      left: 0
      top: 0
      font-size: .4rem
</style>
