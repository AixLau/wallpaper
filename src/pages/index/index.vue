<!-- 使用 type="home" 属性设置首页，其他页面不需要设置，默认为page；推荐使用json5，更强大，且允许注释 -->
<route lang="json5" type="home">
{
style: {
navigationStyle: 'custom',
navigationBarTitleText: '首页',
},
}
</route>
<template>
  <view class="homeLayout pageBackgroundCol ">
    <view>
      <view class="banner">
        <wd-swiper
            :list="swiperList"
            autoplay
            v-model:current="current"
            :indicator="{ type: 'dots-bar' }"
            @click="handleClick"
            @change="onChange"
        ></wd-swiper>
      </view>

      <view class="notice">
        <view class="left">
          <wd-icon class="icon" name="tips" size="22px" color="#0083ff"></wd-icon>
          <text class="text">公告</text>
        </view>
        <view class="center">
          <swiper vertical autoplay interval="1500" duration="500" circular>
            <swiper-item v-for="item in 3">公告 {{ item }}</swiper-item>
          </swiper>
        </view>
        <view class="right">
          <wd-icon name="arrow-right" size="22px" color="#0083ff"></wd-icon>
        </view>
      </view>

      <view class="select">
        <common-title>
          <template #left>每日推荐</template>
          <template #right>
            <wd-icon name="calendar" size="22px" class="mr-[10rpx]"/>
            {{ new Date().getDate() }}日
          </template>
        </common-title>
        <view class="content">
          <scroll-view scroll-x>
            <view class="box" v-for="item in swiperList">
              <image :src="item" mode="aspectFill"></image>
            </view>
          </scroll-view>
        </view>
      </view>

      <view class="theme m-y-[50rpx]">
        <common-title>
          <template #left>精选专题</template>
          <template #right>
            <navigator>更多</navigator>
          </template>
        </common-title>
        <view class="mt-[30rpx] px-[30rpx]">
          <theme-item :items="themeItemList"/>
        </view>
      </view>
    </view>
  </view>
</template>

<script lang="ts" setup>
import CommonTitle from '@/components/common-title.vue'
import ThemeItem from '@/components/theme-item.vue'
import {ThemeItemProps} from '@/types/theme-item'
// 获取屏幕边界到安全区域距离
const { safeAreaInsets } = uni.getSystemInfoSync()
defineOptions({
  name: 'Home',
})
const current = ref<number>(0)

const swiperList = ref([
  'https://registry.npmmirror.com/wot-design-uni-assets/*/files/redpanda.jpg',
  'https://registry.npmmirror.com/wot-design-uni-assets/*/files/capybara.jpg',
  'https://registry.npmmirror.com/wot-design-uni-assets/*/files/panda.jpg',
  'https://registry.npmmirror.com/wot-design-uni-assets/*/files/moon.jpg',
  'https://registry.npmmirror.com/wot-design-uni-assets/*/files/meng.jpg',
])

function handleClick(e) {
  console.log(e)
}

function onChange(e) {
  console.log(e)
}

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

<style lang="scss" scoped>
.homeLayout {
  .banner {
    padding: 30rpx;
  }

  .notice {
    display: flex;
    width: 690rpx;
    height: 80rpx;
    margin: 0 auto;
    line-height: 80rpx;
    background-color: #f9f9f9;
    border-radius: 80rpx;

    .left {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 140rpx;

      .icon {
        padding-right: 5rpx;
      }

      .text {
        font-size: 28rpx;
        font-weight: 600;
      }
    }

    .center {
      flex: 1;

      swiper {
        height: 100%;

        swiper-item {
          height: 100%;
          overflow: hidden;
          text-overflow: ellipsis;
          white-space: nowrap;
        }
      }
    }

    .right {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 70rpx;
    }
  }

  .select {
    padding-top: 50rpx;

    .content {
      width: 720rpx;
      margin-top: 30rpx;
      margin-left: 30rpx;

      scroll-view {
        white-space: nowrap;

        .box {
          display: inline-block;
          width: 200rpx;
          height: 440rpx;
          margin-left: 20rpx;

          image {
            width: 100%;
            height: 100%;
            border-radius: 12rpx;
          }
        }
      }
    }
  }
}
</style>
