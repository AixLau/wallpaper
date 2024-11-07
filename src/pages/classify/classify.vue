<route lang="json5">
{
style: {
navigationBarTitleText: '分类',
},
}
</route>
<template>
  <view>
    <view class="px-[30rpx]">
      <theme-item :items="themeItemList"/>
    </view>
  </view>
</template>

<script setup lang="ts">

import ThemeItem from "@/components/theme-item.vue";
import {ThemeItemProps} from "@/types/theme-item";

const themeItemList: ThemeItemProps[] = [
  {
    title: '红熊猫',
    url: 'https://registry.npmmirror.com/wot-design-uni-assets/*/files/redpanda.jpg',
    path: '/redpanda',
    updateInfo: '3天前更新',
  },
  {
    title: '水豚',
    url: 'https://registry.npmmirror.com/wot-design-uni-assets/*/files/capybara.jpg',
    path: '/capybara',
    updateInfo: '5天前更新',
  },
  {
    title: '熊猫',
    url: 'https://registry.npmmirror.com/wot-design-uni-assets/*/files/panda.jpg',
    path: '/panda',
    updateInfo: '1周前更新',
  },
  {
    title: '月亮',
    url: 'https://registry.npmmirror.com/wot-design-uni-assets/*/files/moon.jpg',
    path: '/moon',
    updateInfo: '10天前更新',
  },
  {
    title: '萌宠',
    url: 'https://registry.npmmirror.com/wot-design-uni-assets/*/files/meng.jpg',
    path: '/meng',
    updateInfo: '2周前更新',
  },
  {
    title: '萌宠',
    url: 'https://registry.npmmirror.com/wot-design-uni-assets/*/files/meng.jpg',
    path: '/meng',
    updateInfo: '2周前更新',
  },
]
</script>


<style scoped lang="scss">

</style>
