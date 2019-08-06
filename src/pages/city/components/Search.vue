<template lang="html">
  <div>
    <div class="search">
      <input v-model="keyWord" type="text" class="search-input" placeholder="输入城市名称或拼音" name="" value="">
    </div>
    <div class="search-content" v-show="keyWord" ref="search">
      <ul>
        <li v-for="item in list" :key="item.id" @click="handleCityClick(item.name)">{{item.name}}</li>
        <li v-show="!list.length">没有找到匹配数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
import { mapMutations } from 'vuex'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyWord: '',
      list: [],
      timer: null
    }
  },
  watch: {
    keyWord () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyWord) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyWord) > -1 || value.name.indexOf(this.keyWord) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  },
  methods: {
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  }
}
</script>

<style lang="stylus" scoped>
  .search
    width: 100%
    height: .72rem
    background-color: #00bcd4
    position: relative
    padding: .05rem .1rem
    box-sizing: border-box;
    .search-input
      width: 100%
      height: .62rem
      border-radius: .06rem
      padding: 0 .1rem
  .search-content
    overflow: hidden
    position: absolute
    top:1.6rem
    left: 0
    right: 0
    bottom: 0
    background-color: #efefef
    z-index: 999
    li
      height: .9rem;
      border-bottom: .02rem solid #ddd;
      line-height: .9rem;
      text-indent: .2rem
</style>
