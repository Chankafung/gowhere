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
      }
    }
  },
  props: {
    iconList: Array
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
        height: 3.5rem
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
