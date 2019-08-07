<template>
  <div>
    <div class="recommend-title">
      <img src="http://img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" alt="">
      <span>猜你喜欢</span>
    </div>
    <ul>
      <router-link tag="li" :to="'/detail/'+item.id" class="item border-bottom" v-for="item in recommendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" alt="">
        </div>
        <div class="item-content-wrapper">
          <p>{{item.title}}</p>
          <div class="item-content-like">
            <span class="item-like">
              <strong class="item-like-full" :style="{width:item.width}"></strong>
              <span class="item-like-grey"></span>
            </span>
            <span class="item-discuss">{{item.discuss}}条评论</span>
          </div>
          <div class="item-content-price">
            <span>￥<em>{{item.price}}</em></span>起
            <span>{{item.area}}</span>
          </div>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    recommendList: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  /* 声明字体 */
  @font-face{
      font-family: 'mpiconfont';
      src:url('~styles/iconfont/mpiconfont.ttf')
  }
  .recommend-title
    padding: .24rem 0
    border-top: .2rem solid #f5f5f5
    img
      width: .3rem
      height: .3rem
      margin-left: .2rem
      vertical-align: sub
    span
      font-size: .32rem
      line-height: .44rem
  .item
    padding: .2rem .24rem
    a
      display: block
      width: 100%
      height: 100%
      &:after
        content: " "
        display:block
        height:0
        visibility:hidden
        font-size:0
        clear:both
        overflow: hidden
    .item-img-wrapper
      width: 2rem
      height: 2rem
      float: left
      .item-img
        width: 100%
    .item-content-wrapper
      padding-left: .22rem
      overflow: hidden
      p
        margin-top: .26rem
        font-size: .32rem
        height: .44rem;
        line-height: .44rem
        color: #333
        ellipsis()
      .item-content-like
        margin-top: .14rem
        height: .34rem
        .item-like
          display: inline-block
          position: relative
          width: 1.4rem
          height: .28rem
          .item-like-full
            color: #ffb436
            font-family: 'mpiconfont'
            font-size: .28rem
            position: absolute
            left: 0
            z-index: 2
            overflow: hidden
          .item-like-grey
            color: #e0e0e0
            font-family: 'mpiconfont'
            font-size: .28rem
            position: absolute
            left: 0
            z-index: 1
        .item-discuss
          font-size: .24rem
          color: #616161
          vertical-align: top
          margin-left: .18rem
          font-size: .24rem
      .item-content-price
        margin-top: .22rem
        font-size: .24rem
        color: #333
        position: relative
        span:nth-child(1)
          color: #ff8300
          em
            font-size: .4rem
        span:nth-child(2)
          position: absolute
          right: 0
          bottom: 0
</style>
