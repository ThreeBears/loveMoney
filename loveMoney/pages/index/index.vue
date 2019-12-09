<template>
  <view class="content">
    <view class="text-area">
      <uni-nav-bar>
        <view slot="left" class="left-title">iMoney</view>
        <view slot="right">
          <div class="nav-right">
            <span class="money">￥1.00</span>
            <span class="getcash">
              立即提现
              <uni-icons type="forward" size="14" color="#aaa"></uni-icons>
            </span>
          </div>
        </view>
      </uni-nav-bar>
    </view>
    <view class="swiper-wrapper">
      <swiper
        class="swiper"
        :indicator-dots="indicatorDots"
        :autoplay="autoplay"
        :interval="interval"
        :duration="duration"
        :circular="circular"
      >
        <swiper-item>
          <view class="swiper-item">
            <div class="bg1"></div>
          </view>
        </swiper-item>
        <swiper-item>
          <view class="swiper-item">
            <div class="bg2"></div>
          </view>
        </swiper-item>
        <swiper-item>
          <view class="swiper-item">
            <div class="bg3"></div>
          </view>
        </swiper-item>
      </swiper>
    </view>
    <!-- <common-tab></common-tab> -->
	<x-scroll-list :tabTitle="tabTitle"></x-scroll-list>
  </view>
</template>

<script>
import uniNavBar from "@/components/uni-nav-bar/uni-nav-bar.vue";
import uniIcons from "@/components/uni-icons/uni-icons.vue";
import xScrollList from "@/components/common/x-scroll-list.vue"
export default {
  data() {
    return {
      title: "首页",
      indicatorDots: true,
      autoplay: false,
      interval: 1000,
      duration: 500,
	  circular: true,
	  tabTitle:['常规任务','快赚','小程序任务','游戏任务','App试玩','游戏试玩','更多']
    };
  },
  onLoad() {},
  methods: {
	  changeTab(index){
		  console.log(`第${index}个菜单`);
	  }
  },
  components: {
    uniNavBar,
	uniIcons,
	uniTabs,
	xScrollList
  }
};
</script>

<style lang="scss" scoped>
.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.swiper-wrapper {
  width: 100%;
  .swiper {
    &-item {
      height: 100%;
      .bg1,
      .bg2,
      .bg3 {
        background-size: contain;
        background-position: center center;
        height: 100%;
      }
      .bg1 {
        background-image: url("../../static/imgs/task1.png");
      }
      .bg2 {
        background-image: url("../../static/imgs/task2.png");
      }
      .bg3 {
        background-image: url("../../static/imgs/task3.png");
      }
    }
  }
}

.text-area {
  display: flex;
  justify-content: center;
  .left-title {
    color: #eb5e7b;
  }
  .nav-right {
    min-width: 160px;
    .money {
      margin-right: 3px;
      color: #e7b843;
    }
    .getcash {
      font-size: 13px;
      color: #aaa;
    }
  }
}
</style>
