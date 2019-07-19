<template lang="html">
  <div>
    <div class="list">
      <div class="area">
        <div class="title">当前城市</div>
        <div class="button-now">南京</div>
      </div>
      <div class="area">
        <div class="title">热门城市</div>
        <ul class="button-list">
          <li v-for="item of hotList" :key="item.id">{{item.city}}</li>
        </ul>
      </div>
      <div class="area">
        <div class="title">A</div>
        <ul class="button-list">
          <li v-for="item of hotList" :key="item.id">{{item.city}}</li>
        </ul>
      </div>
      <div class="area">
        <div class="title">A</div>
        <ul class="button-list">
          <li v-for="item of hotList" :key="item.id">{{item.city}}</li>
        </ul>
      </div>
      <div class="area">
        <div class="title">A</div>
        <ul class="button-list">
          <li v-for="item of hotList" :key="item.id">{{item.city}}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CityList',
  data () {
    return {
      hotList: [
        {
          id: '0001',
          city: '北京'
        },
        {
          id: '0002',
          city: '上海'
        },
        {
          id: '0003',
          city: '三亚'
        },
        {
          id: '0004',
          city: '香港'
        },
        {
          id: '0005',
          city: '杭州'
        },
        {
          id: '0006',
          city: '广州'
        },
        {
          id: '0007',
          city: '成都'
        },
        {
          id: '0008',
          city: '深圳'
        },
        {
          id: '0009',
          city: '苏州'
        },
        {
          id: '0010',
          city: '桂林'
        },
        {
          id: '0011',
          city: '西安'
        },
        {
          id: '0012',
          city: '厦门'
        }
      ]
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
