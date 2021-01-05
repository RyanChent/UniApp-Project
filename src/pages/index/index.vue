<template>
  <view class="content">
    <image class="logo" src="../../static/logo.png"></image>
    <view>
      <text class="title">{{ title }}</text>
      <van-button type="primary">主要按钮</van-button>
    </view>
  </view>
</template>

<script lang="ts">
import { Component,Vue ,Watch} from "vue-property-decorator";
@Component({})
export default class Index extends Vue {
  private title: String = 'Hello World'
  onLoad() {}
}
</script>

<style>
.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.logo {
  height: 200rpx;
  width: 200rpx;
  margin: 200rpx auto 50rpx auto;
}

.text-area {
  display: flex;
  justify-content: center;
}

.title {
  font-size: 36rpx;
  color: #8f8f94;
}
</style>
