<template lang="html">
  <div>
    <div class="banner">
      <img class="banner-img" src="http://img1.qunarzz.com/sight/p0/1511/ea/eaf1bdc38aed9e6690.img.jpg_600x330_5597540f.jpg" alt="">
      <div class="banner-info">
        <div class="banner-title">银杏湖乐园</div>
        <div class="banner-number"><span class="iconfont">&#xe606;</span>18</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailBanner'
}
</script>

<style lang="stylus" scoped>
  .banner
    overflow: hidden
    height: 0
    padding-bottom: 55%
    position: relative
    .banner-img
      width: 100%
      vertical-align: top
    .banner-info
      display: flex
      position: absolute
      left: 0
      right: 0
      bottom: 0
      line-height: .6rem
      color: #fff
      .banner-title
        flex: 1
        font-size: .32rem
        padding: 0 .2rem
      .banner-number
        padding: 0 .4rem
        height: .32rem
        line-height: .32rem
        border-radius: .2rem
        font-size: .24rem
        background: rgba(0, 0, 0, 0.8)
        margin-top: .14rem
        .iconfont
          font-size: .24rem
</style>
