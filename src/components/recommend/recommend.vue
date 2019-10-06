<template>
  <div class="recommend" ref="recommend">
    <!-- 在这一层做引用，初始化BScroll，数据加载后在渲染，要记得加上data -->
    <div ref="scroll" class="recommend-content">
      <!-- BScroll的层级是父子级，子级只有第一个元素才会滚动，想要下面两个同级的div同时滚动，需要在外层包裹一层div，作为外层的一个子元素， -->
      <div>
        <!-- 从服务端加载数据，会有延迟，等抓到数据后，在加载slider组件，这样slider里的mounted周期就能拿到数据了 -->
        <div class="slider-wrapper">
        </div>
        <div class="recommend-list">
          <h1 class="list-title">热门歌单推荐</h1>
          <ul>
            <li>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped lang="stylus">
 @import "~common/stylus/variable"
  .recommend
    position: fixed
    width: 100%
    top: 88px
    bottom: 0
    .recommend-content
      height: 100%
      overflow: hidden
      .slider-wrapper
        position: relative
        width: 100%
        overflow: hidden
      .recommend-list
        .list-title
          height: 65px
          line-height: 65px
          text-align: center
          font-size: $font-size-medium
          color: $color-theme
        .item
          display: flex
          box-sizing: border-box
          align-items: center
          padding: 0 20px 20px 20px
          .icon
            flex: 0 0 60px
            width: 60px
            padding-right: 20px
          .text
            display: flex
            flex-direction: column
            justify-content: center
            flex: 1
            line-height: 20px
            overflow: hidden
            font-size: $font-size-medium
            .name
              margin-bottom: 10px
              color: $color-text
            .desc
              color: $color-text-d
      .loading-container
        position: absolute
        width: 100%
        top: 50%
        transform: translateY(-50%)
</style>
