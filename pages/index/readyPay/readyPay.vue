<template>
	<view>
		<view class="header">
			<image @click="goReturn" class="returnIcon" src="../../../static/index/pay/return.png" mode=""></image>
			<view class="headerTitle">下单支付</view>
		</view>
		<view class="paddingView">
			<view class="orderMsg">
				<view class="title">智慧行李</view>
				<view class="priceMsg">
					<view class="left">应付总额：</view>
					<view class="right">
						<view class="unit">￥</view>
						<view class="number">{{payNum}}</view>
					</view>
				</view>
			</view>
			<view class="payType">
				<view @click="currentIndex = index" class="item" v-for="(item,index) in payType" :key="index">
					<image class="typeIcon" :src="item.typeIcon" mode=""></image>
					<view class="typeText">{{item.typeText}}</view>
					<image class="selected" v-if="currentIndex === index " :src="item.selected" mode=""></image>
					<image class="notSelect" v-else :src="item.notSelect" mode=""></image>
				</view>
			</view>
			<view class="payBtn" @click="submit">立即支付</view>
			
			<view class="mask" @click="isShowMask = !isShowMask" v-if="isShowMask">
				<view class="whiteView">
					<view class="maskTitle">您的订单尚未完成支付，确定要离开吗？</view>
					<view class="maskBtn">
						<view class="lBtn" @click="isShowMask = !isShowMask">继续支付</view>
						<view class="rBtn" @click="sureReturn">确定离开</view>
					</view>
				</view>
				
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				payNum: 49.00,
				payType: [
					{
						typeIcon: "../../../static/index/pay/pay1.png",
						typeText: '微信支付',
						notSelect: "../../../static/index/pay/notSelect.png",
						selected: "../../../static/index/pay/selected.png"
					},
					{
						typeIcon: "../../../static/index/pay/pay1.png",
						typeText: '余额支付',
						notSelect: "../../../static/index/pay/notSelect.png",
						selected: "../../../static/index/pay/selected.png"
					}
				],
				currentIndex: '',
				isShowMask: false
			}
		},
		methods: {
			// selectPayType(index) {
			// 	this.currentIndex = index
			// }
			goReturn() {
				this.isShowMask = true
			},
			submit() {
				uni.showModal({
					title: '是否确认支付？',
					success: res => {
						uni.navigateTo({
							url: '/pages/index/readyPay/payOk/payOk'
						})
					}
				})
			},
			sureReturn() {
				uni.navigateBack({
					url: '/pages/index/index'
				})
			}
		},
		// onBackPress(e) {
		// 	console.log("e")
		// },
		// onHide() {
		// 	uni.showToast({
		// 	    title: '标题',
		// 	    duration: 2000
		// 	});
		// }
	}
</script>

<style lang="less">
	.header {
		padding: 0 30rpx;
		height: 98rpx;
		background-color: #FFFFFF;
		box-sizing: border-box;
		display: flex;
		align-items: center;
		.returnIcon {
			width: 16rpx;
			height: 28rpx;
		}
		.headerTitle {
			color: #222222;
			margin-left: 24rpx;
			font-size: 36rpx;
			font-weight: bold;
		}
	}
	.paddingView {
		padding: 28rpx;
		.orderMsg {
			background-color: #FFFFFF;
			border-radius: 12rpx;
			.title {
				border-bottom: 1px solid #F7F8FA;
				padding: 24rpx 28rpx;
				font-size: 28rpx;
				color: #222222;
				font-weight: bold;
			}
			.priceMsg {
				height: 110rpx;
				display: flex;
				align-items: center;
				padding: 0 26rpx;
				font-weight: bold;
				.left {
					color: #999999;
					font-size: 28rpx;
				}
				.right {
					color: #FD6A28;
					display: flex;
					align-items: center;
					.unit {
						font-size: 32rpx;
					}
					.number {
						font-size: 44rpx;
						margin-left: 6rpx;
					}
				}
			}
		}
		.payType {
			background-color: #FFFFFF;
			margin-top: 28rpx;
			border-radius: 12rpx;
			.item {
				display: flex;
				align-items: center;
				padding: 0 28rpx;
				height: 92rpx;
				border-bottom: 1px solid #F7F8FA;
				&:last-child {
					border-bottom: 0;
				}
				.typeIcon {
					width: 40rpx;
					height: 34.68rpx;
				}
				.typeText {
					font-size: 32rpx;
					font-weight: bold;
					margin-left: 18rpx;
					color: #222222;
				}
				// .selectIcon {
				// 	width: 40rpx;
				// 	height: 40rpx;
				// 	margin-left: auto;
				// }
				.notSelect {
					width: 40rpx;
					height: 40rpx;
					margin-left: auto;
				}
				.selected {
					width: 40rpx;
					height: 40rpx;
					margin-left: auto; 
				}
			}
		}
		.payBtn {
			margin-top: 72rpx;
			background: linear-gradient(90deg,#28A032 0%, #50C414 100%);
			border-radius: 12rpx;
			color: #FFFFFF;
			height: 98rpx;
			line-height: 98rpx;
			text-align: center;
			font-size: 36rpx;
		}
	}
	
	//遮罩层样式
	.mask {
		position: fixed;
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
		background-color: rgba(34,34,34,0.5);
		display: flex;
		justify-content: center;
		align-items: center;
		.whiteView {
			background-color: #FFFFFF;
			width: 592rpx;
			height: 304rpx;
			overflow: hidden;
			border-radius: 12rpx;
			.maskTitle {
				height: 160rpx;
				display: flex;
				justify-content: center;
				align-items: center;
				font-size: 28rpx;
				font-weight: bold;
				color: #222222;
			}
			.maskBtn {
				display: flex;
				justify-content: space-between;
				align-items: center;
				padding: 0 70rpx;
				.lBtn,.rBtn {
					display: flex;
					justify-content: center;
					align-items: center;
					width: 196rpx;
					height: 88rpx;
					font-size: 28rpx;
					border-radius: 12rpx;
					font-weight: bold;
				}
				.lBtn {
					border: 1px solid #28A032;
					color: #28A032;
				}
				.rBtn {
					background-color: #28A032;
					color: #FFFFFF;
				}
			}
		}
	}
</style>
