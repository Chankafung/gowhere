<template lang="html">
  <div>
    <ul class="alphabet">
      <li v-for="item of letters" :key="item" :ref="item" @click="handleLetterClick" @touchstart="handleTouchstart" @touchmove="handleTouchmove" @touchend="handleTouchend">{{item}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  data () {
    return {
      touchStatus: false,
      startY: 0,
      timer: null
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  methods: {
    handleLetterClick (e) {
      this.$emit('change', e.target.innerText)
    },
    handleTouchstart (e) {
      this.touchStatus = true
    },
    handleTouchmove (e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 44
          const index = Math.floor((touchY - this.startY) / 20)
          if (index >= 0 && index < this.letters.length) {
            this.$emit('change', this.letters[index])
          }
        }, 16)
      }
    },
    handleTouchend (e) {
      this.touchStatus = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .alphabet
    position: absolute
    right: 0
    top: .88rem
    bottom: 0
    width: .4rem
    display: flex
    flex-direction: column
    justify-content: center
    z-index: 11
    li
      color: #00bcd4
      text-align: center
      line-height: .4rem
</style>
