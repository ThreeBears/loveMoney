<template>
	<view class="content">
		<!-- <image class="logo" src="/static/logo.png"></image> -->
		<view class="text-area">
			<uni-nav-bar>
				<view slot="left">iMoney</view>
				<view slot="right">
					<div class='nav-right'>
						<span class='money'>￥1.00 </span>
						<span class='getcash'>立即提现 ＞</span>
					</div></view>
			</uni-nav-bar>
		</view>
	</view>
</template>

<script>
	import uniNavBar from "@/components/uni-nav-bar/uni-nav-bar.vue"
	export default {
		data() {
			return {
				title: '首页'
			}
		},
		onLoad() {

		},
		methods: {

		},
		components: {uniNavBar}
	}
</script>

<style lang="scss" scoped>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.text-area {
		display: flex;
		justify-content: center;
		.nav-right{
			min-width:180px;
			.money{
				margin-right:3px;
			}
			.getcash{}
		}
	}

</style>
