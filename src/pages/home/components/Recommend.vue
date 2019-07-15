<template>
  <div>
    <div class="recommend-title">
      <img src="http://img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" alt="">
      <span>猜你喜欢</span>
    </div>
    <ul>
      <li class="item border-bottom" v-for="item in recommendList" :key="item.id">
        <a href="#">
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
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1511/ea/eaf1bdc38aed9e6690.img.jpg_200x200_3032bf56.jpg',
          title: '银杏湖乐园',
          width: '98%',
          discuss: '3401',
          price: '94.8',
          area: '江宁区'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1907/df/dfe043ff2829f50ca3.img.jpg_200x200_6de74461.jpg',
          title: '南京海底世界',
          width: '98%',
          discuss: '7292',
          price: '100',
          area: '玄武区'
        },
        {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1904/31/3151f5637e832d86a3.img.jpg_200x200_a19ed206.jpg',
          title: '南京万达乐园',
          width: '98%',
          discuss: '625',
          price: '138',
          area: '栖霞区'
        },
        {
          id: '0004',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1411/bb/538133c76765880a3d3c802e45015c57.water.jpg_200x200_169b048c.jpg',
          title: '紫清湖生态温泉',
          width: '98%',
          discuss: '1805',
          price: '107.7',
          area: '江宁区'
        },
        {
          id: '0005',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/201406/04/4f597aad25208a233999238c65af9b06.jpg_200x200_d1ea2bd2.jpg',
          title: '南京珍珠泉水上世界',
          width: '100%',
          discuss: '673',
          price: '93.9',
          area: '珍珠泉'
        },
        {
          id: '0006',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1805/9b/9b3cbcf2624bf8cea3.img.jpg_200x200_075bc9ef.jpg',
          title: '弘阳未来世界主题乐园',
          width: '94%',
          discuss: '1052',
          price: '51',
          area: '浦口区'
        },
        {
          id: '0007',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1906/58/588b13f236575746a3.img.jpg_200x200_cb23ae6f.jpg',
          title: '南京欢乐水魔方',
          width: '94%',
          discuss: '2510',
          price: '180',
          area: '江宁区'
        }
      ]
    }
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
