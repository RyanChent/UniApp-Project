<template>
<uni-shadow-root class="@vant-grid-index"><view :class="'van-grid custom-class '+(border && !gutter ? 'van-hairline--top' : '')" :style="computed.rootStyle({ gutter })">
  <slot></slot>
</view></uni-shadow-root>
</template>
<wxs src="./index.wxs" module="computed"></wxs>
<script>

global['__wxRoute'] = '@vant/grid/index'
import { VantComponent } from '../common/component';
VantComponent({
  relation: {
    name: 'grid-item',
    type: 'descendant',
    current: 'grid',
  },
  props: {
    square: {
      type: Boolean,
      observer: 'updateChildren',
    },
    gutter: {
      type: [Number, String],
      value: 0,
      observer: 'updateChildren',
    },
    clickable: {
      type: Boolean,
      observer: 'updateChildren',
    },
    columnNum: {
      type: Number,
      value: 4,
      observer: 'updateChildren',
    },
    center: {
      type: Boolean,
      value: true,
      observer: 'updateChildren',
    },
    border: {
      type: Boolean,
      value: true,
      observer: 'updateChildren',
    },
    direction: {
      type: String,
      observer: 'updateChildren',
    },
    iconSize: {
      type: String,
      observer: 'updateChildren',
    },
  },
  methods: {
    updateChildren() {
      this.children.forEach((child) => {
        child.updateStyle();
      });
    },
  },
});
export default global['__wxComponents']['@vant/grid/index']
</script>
<style platform="mp-weixin">
@import '../common/index.css';.van-grid{position:relative;box-sizing:border-box;overflow:hidden}
</style>