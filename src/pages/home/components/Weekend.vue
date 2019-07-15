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
  data () {
    return {
      weekendList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/f1/ae9d4299b8aaea.jpg_r_640x214_0c555905.jpg',
          title: '南京必打卡',
          desc: '看尽王侯将相荣辱成败，六朝金粉潮起潮落'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/e1/cdbf56d837da59.jpg_r_640x214_105fc3f2.jpg',
          title: '民国情怀国共风华',
          desc: '南京，一座历史文化名城，这片土地上曾经经历过太多太多值得我们去追忆的往事'
        },
        {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/f3/d51669250308cc.jpg_r_640x214_7a127cd0.jpg',
          title: '秦淮金粉里的南京',
          desc: '欣赏秦淮风光上独具特色的人文景观，夫子庙里深刻体会古代科举制度'
        },
        {
          id: '0004',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1811/58/a02ad3ab47e3e3.jpg_r_640x214_08977098.jpg',
          title: '扬州大明寺',
          desc: '大明寺扬州第一名胜，集佛教庙宇、文物古迹和园林风光于一体的游览胜地'
        },
        {
          id: '0005',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1603/ff/19b65f7ca38d70.jpg_r_640x214_c9a4a14b.jpg',
          title: '长江烂漫景',
          desc: '览滚滚长江，看山花烂漫'
        }
      ]
    }
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
      overflow: hidden;
      color: #616161;
      font-size: .24rem;
      line-height: .42rem;
      padding-left: .2rem
      padding-bottom: .2rem
      ellipsis()
</style>
