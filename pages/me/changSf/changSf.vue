<template>
	<view>
		<view class="userHeader">
			<image class="avatar" src="../../../static/me/defaultAvatar.png" mode=""></image>
			<view class="lable">
				18673236573
			</view>
		</view>
		<view class="whiteBox">
			<view class="item" v-for="(item,index) in nav" :key="index">
				<image class="icon" :src="item.icon" mode=""></image>
				<view class="text">{{item.label}}</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				nav: [
					{
						label: '我要寄件',
						icon: '../../../static/me/changeSf/nav1.png',
						url: ''
					},
					{
						label: '寄存点人员',
						icon: '../../../static/me/changeSf/nav2.png',
						url: ''
					},
					{
						label: '跑腿人员',
						icon: '../../../static/me/changeSf/nav3.png',
						url: ''
					},
					{
						label: '驻点人员',
						icon: '../../../static/me/changeSf/nav4.png',
						url: ''
					}
				]
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="less">
	page {
		background-color: #F3F3F3;
	}
	.userHeader {
		background-image: url(../../../static/me/bg.png);
		width: 750rpx;
		height: 288rpx;
		position: relative;
		text-align: center;
		padding: 44rpx 0;
		background-size: cover;
		.avatar {
			width: 116rpx;
			height: 116rpx;
		}
		.lable {
			margin-top: 36rpx;
			font-size: 36rpx;
			color: #FFFFFF;
		}
	}
	.whiteBox {
		background-color: #FFFFFF;
		border-radius: 12rpx;
		display: flex;
		flex-wrap: wrap;
		width: 694rpx;
		margin: 40rpx auto 0;
		.item {
			width: 50%;
			height: 194rpx;
			border-bottom: 1px solid #EBEBEB;
			border-right: 1px solid #EBEBEB;
			display: flex;
			align-items: center;
			padding: 0 40rpx;
			.icon {
				width: 72rpx;
				height: 72rpx;
			}
			.text {
				font-size: 32rpx;
				margin-left: 24rpx;
				color: #222222;
				font-weight: bold;
			}
			&:nth-child(2n) {
				border-right: none;
			}
			&:nth-child(3) {
				border-bottom: none;
			}
			&:nth-child(4) {
				border-bottom: none;
			}
		}
	}
</style>
