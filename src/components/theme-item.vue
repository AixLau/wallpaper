<template>
  <!-- 循环渲染每个图片块 -->
  <view class="grid grid-cols-3 gap-[15rpx]">
    <view v-for="(item, index) in displayItems" :key="index">
      <navigator
        class="w-full h-[350rpx] border-rd-[12rpx] overflow-hidden pos-relative"
        :url="item.path"
      >
        <image class="w-full h-full" :src="item.url" mode="aspectFill" />
        <!-- 通用样式 -->
        <view v-if="!item.isMore">
          <view
            class="w-full h-[70rpx] pos-absolute bottom-0 left-0 flex items-center justify-center c-white backdrop-blur-lg bg-[rgba(0,0,0,0.2)]"
          >
            {{ item.title }}
          </view>
          <view
            class="p-[10rpx] scale-80 transform-origin-top-left rounded-br-[20rpx] pos-absolute top-0 left-0 c-white bg-[rgba(250,129,90,0.7)] backdrop-blur-[20rpx]"
          >
            {{ item.updateInfo }}
          </view>
        </view>
        <!-- 更多按钮样式 -->
        <view
          v-else
          class="w-full h-full pos-absolute bottom-0 left-0 flex items-center justify-center c-white backdrop-blur-lg bg-[rgba(0,0,0,0.2)]"
        >
          <wd-icon class="rotate-90" name="more" size="22px"></wd-icon>
          更多
        </view>
      </navigator>
    </view>
  </view>
</template>

<script setup lang="ts">
// 使用 props 接收数据数组
import { ThemeItemProps } from '@/types/theme-item'

const props = defineProps<{
  items: ThemeItemProps[]
}>()

// 计算显示的 items 数组，设置最后一个项为“更多”按钮
const displayItems = computed(() => {
  const updatedItems = [...props.items]

  // 将最后一个 item 标记为“更多”项
  if (updatedItems.length > 0) {
    updatedItems[updatedItems.length - 1] = {
      title: '更多',
      path: updatedItems[updatedItems.length - 1].path,
      url: updatedItems[updatedItems.length - 1].url,
      updateInfo: '',
      isMore: true, // 添加 isMore 标记
    }
  }

  return updatedItems
})
</script>

<style scoped lang="scss"></style>
