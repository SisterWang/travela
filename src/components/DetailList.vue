<template>
  <div>
    <div class="item"
         v-for="(item, index) of list"
         :key="index"
    >
      <div class="item-title">
        <span class="item-title-icon border-bottom"></span>
        {{item.title}}
      </div>
      <div v-if="item.children" class="item-children">
        <detail-list :list="item.children"></detail-list>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  .item-title
    line-hight: .8rem
    font-size: .32rem
    padding: 0 .2rem
    .item-title-icon
      position: relative
      display: inline-block
      top: .06rem
      width: .36rem
      height: .36rem
      background: url(//s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
      margin-right: .1rem
      background-size: .4rem 3rem
  .item-children
    padding: 0 .2rem
</style>
