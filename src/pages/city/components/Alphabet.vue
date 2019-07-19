<template lang="html">
  <div>
    <ul class="alphabet">
      <li>A</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'CityAlphabet'
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
    justify-content: center;
    li
      color: #00bcd4
      text-align: center
      line-height: .4rem
</style>
