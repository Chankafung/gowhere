<template>
    <div class="icons">
        <swiper :options="swiperOption">
            <!-- slides -->
            <swiper-slide v-for="(page, index) in pages" :key="index">
                <div class="icon" v-for="item in page" :key="item.id">
                    <a href="#">
                        <div class="icon-img">
                            <img :src="item.imgUrl" alt="">
                        </div>
                        <p>{{item.desc}}</p>
                    </a>
                </div>
            </swiper-slide>
            <!-- Optional controls -->
            <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: false
      },
      iconList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '景点门票'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
          desc: '亲子游'
        },
        {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
          desc: '文化古迹'
        },
        {
          id: '0004',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/97/02f5043b51b2102.png',
          desc: '牛首山'
        },
        {
          id: '0005',
          imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/b71c1387a921ccf9c6edc7e8def3da90.png',
          desc: '红山森林动物园'
        },
        {
          id: '0006',
          imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/94f7f5bf7b0f4d238dd68d718f102f40.png',
          desc: '中山林'
        },
        {
          id: '0007',
          imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/f6dda1876c5950d83cc159c8fd522943.png',
          desc: '总统府'
        },
        {
          id: '0008',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png',
          desc: '银杏湖乐园'
        },
        {
          id: '0009',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
          desc: '大报恩寺'
        },
        {
          id: '0010',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
          desc: '南京海底世界'
        }
      ]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
@import '~styles/mixins.styl'
    .icons >>> .swiper-container
        height: 3.4rem
    .icons >>> .swiper-pagination
        bottom: 0
    .icons >>> .swiper-pagination-bullet
        width: 6px
        height: 6px
    .icons >>> .swiper-pagination-bullet-active
        background: rgba(0,175,190,.8)
    .icons
        height: 0
        height: 3.4rem
        .icon
            width: 25%
            height: 1.5rem
            padding-top: .1rem
            float: left
            text-align: center
            .icon-img
                width: 1.1rem
                height: 1.1rem
                margin: 0 auto
                img
                    width: 1.1rem
                    height: 1.1rem
            p
                color: $darkTextColor
                ellipsis()

</style>
