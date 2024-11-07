<route lang="json5">
{
style: {
navigationBarTitleText: '我的',
},
}
</route>

<template>
  <view>
    <view class="flex items-center justify-center flex-col py-[50rpx]">
      <image class="w-[320rpx] h-[320rpx] border-rd-[50%]" src="../../static/images/faker.webp" mode="aspectFill"/>
      <view class="mt-[30rpx] text-[42rpx]">壁纸</view>
    </view>
    <!-- 动态渲染 sections -->
    <view v-for="(section, sectionIndex) in sections" :key="sectionIndex" class="section">
      <view class="list">
        <view v-for="(row, rowIndex) in section.rows" :key="rowIndex" class="row">
          <view class="left flex items-center">
            <wd-icon :name="row.icon"/>
            <view class="text">{{ row.text }}</view>
          </view>
          <view class="right">
            <wd-icon name="arrow-right" size="22px" color="#0083ff"/>
          </view>
        </view>
      </view>
    </view>
  </view>
</template>

<script lang="ts" setup>
// 定义 sections 数据，包含每个 section 和 row 的内容
const sections = ref([
  {
    rows: [
      { icon: 'add-circle', text: '下载' },
      { icon: 'star', text: '收藏' },
      { icon: 'share', text: '分享' },
    ],
  },
  {
    rows: [
      { icon: 'settings', text: '设置' },
      { icon: 'heart', text: '喜欢' },
      { icon: 'info', text: '关于' },
    ],
  },
]);
</script>

<style lang="scss" scoped>
.section {
  width: 690rpx;
  margin: 50rpx auto;
  border-radius: 20rpx;
  box-shadow: 0 0 30rpx rgba(0, 0, 0, 0.1);

  .list {
    .row {
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 100rpx;
      padding: 0 30rpx;
      border-bottom: 1rpx solid #eeeeee;

      &:last-child {
        border-bottom: 0
      }

      .left {
        display: flex;
        align-items: center;
        gap: 10rpx;
      }

    }
  }
}
</style>
