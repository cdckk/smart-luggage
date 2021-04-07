<template>
	<view class="payOkView">
		<image class="payOkIcon" src="../../../../static/index/pay/selected.png" mode=""></image>
		<view class="title">下单成功</view>
		<view class="text">取件码已由短信下发至您的手机</view>
		<view class="btnBox">
			<view class="l" @click="goHome">返回首页</view>
			<view class="r" @click="goHome">查看订单</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			goHome() {
				uni.reLaunch({
					url: '/pages/index/index'
				})
			}
		}
	}
</script>

<style lang="less">
	.payOkView {
		.payOkIcon {
			width: 120rpx;
			height: 120rpx;
			display: block;
			margin: 100rpx auto 0;
		}
		.title {
			text-align: center;
			font-size: 36rpx;
			color: #222222;
			margin-top: 52rpx;
		}
		.text {
			text-align: center;
			margin-top: 30rpx;
			font-size: 26rpx;
			color: #666666;
		}
		.btnBox {
			margin-top: 112rpx;
			display: flex;
			align-items: center;
			justify-content: space-around;
			.l,.r {
				display: flex;
				align-items: center;
				justify-content: center;
				width: 196rpx;
				height: 88rpx;
				border-radius: 12rpx;
				font-size: 32rpx;
			}
			.l {
				background-color: #D7F0E2;
				color: #28A032;
			}
			.r {
				background-color: #28A032;
				color: #FFFFFF;
			}
		}
	}
</style>
