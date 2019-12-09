<template>
    <view>
        <swiper style="min-height: 100vh;" :current="currentTab" @change="swiperTab">
			<swiper-item v-for="(listItem,listIndex) in list" :key="listIndex">
				<scroll-view style="height: 100%;" scroll-y="true" @scrolltolower="lower1" scroll-with-animation :scroll-into-view="toView">
				<view :id="'top'+listIndex" style="width: 100%;height: 180upx;">边距盒子</view>
				<view class='content' v-if="listItem.length > 0">
					<view class='card' v-for="(item,index) in listItem" :key="index">
						{{item}}
					</view>
				</view>
				<view class='noCard' v-if="listItem.length===0">
					暂无信息
				</view>
				<view style="width: 100%;height: 100upx;opacity:0;">底部占位盒子</view>
				</scroll-view>
			</swiper-item>
		</swiper>
    </view>
  
</template>

<script>
export default {
    data(){
        return {
            currentTab: 0, //sweiper所在页
            list: [[1, 2, 3, 4, 5, 6],['a', 'b', 'c', 'd', 'e', 'f'],[],['2233','4234','13144','324244'],[1, 2, 3, 4, 5, 6],['a', 'b', 'c', 'd', 'e', 'f'],['7'],['8'],['9号']]//数据格式

        }
    }

}
</script>

<style lang="scss">

</style>