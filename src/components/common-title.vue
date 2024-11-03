<template>
  <view class="flex items-center justify-between px-[30rpx]">
    <view class="text-[40rpx]">
      <slot name="left"></slot>
    </view>
    <view class="flex items-center justify-center">
      <slot name="right"></slot>
    </view>
  </view>
</template>

<script setup></script>

<style lang="scss" scoped></style>
