<route lang="json5">
{
style: {
navigationStyle: 'custom',
navigationBarTitleText: '分类列表',
},
}
</route>
<template>
  <view class="h-vh w-[100%]">
    <wd-swiper :list="swiperList" v-model:current="current"
               @click="handleClick" @change="onChange"
               height="100vh"/>
  </view>
</template>

<script setup lang="ts">
const current = ref()
const swiperList = ref([
  'https://registry.npmmirror.com/wot-design-uni-assets/*/files/redpanda.jpg',
  'https://registry.npmmirror.com/wot-design-uni-assets/*/files/capybara.jpg',
  'https://registry.npmmirror.com/wot-design-uni-assets/*/files/panda.jpg',
  'https://registry.npmmirror.com/wot-design-uni-assets/*/files/moon.jpg',
  'https://registry.npmmirror.com/wot-design-uni-assets/*/files/meng.jpg'
])

function handleClick(e) {
  console.log(e)
}

function onChange(e) {
  console.log(e)
}
</script>


<style scoped lang="scss">

</style>
