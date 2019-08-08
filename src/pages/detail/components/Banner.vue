<template lang="html">
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="http://img1.qunarzz.com/sight/p0/1511/ea/eaf1bdc38aed9e6690.img.jpg_600x330_5597540f.jpg" alt="">
      <div class="banner-info">
        <div class="banner-title">银杏湖乐园</div>
        <div class="banner-number"><span class="iconfont">&#xe606;</span> 18</div>
      </div>
    </div>
    <gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClick"></gallary>
  </div>
</template>

<script>
import Gallary from '../../../common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1511/94/94fd49f633a5eb5590.img.jpg_r_800x800_beb76153.jpg', 'http://img1.qunarzz.com/sight/p0/1511/38/384529f35d2c1ff690.img.jpg_r_800x800_e6377ad4.jpg']
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClick () {
      this.showGallary = false
    }
  },
  components: {
    Gallary
  }
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
      background-image: linear-gradient(top, rgba(0, 0, 0, 0),rgba(0, 0, 0, 0.8));
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
