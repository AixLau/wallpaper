<route lang="json5">
{
style: {
navigationBarTitleText: '分类列表',
},
}
</route>
<template>
  <view class="classifyListLayout">
    <view class="grid grid-cols-3 gap-[15rpx] p-[20rpx]">
      <navigator class="h-[480rpx]" url="" v-for="item in 10">
        <image class="w-[100%] h-[100%] rd-2 block"  src="https://alist.aixcc.top/d/%E4%BA%91%E6%9C%8D%E5%8A%A1%E5%99%A8/aix/2.JPEG" mode="aspectFill"/>
      </navigator>
    </view>
  </view>
</template>

<script setup lang="ts">

</script>


<style scoped lang="scss">

</style>
