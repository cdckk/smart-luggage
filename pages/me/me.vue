<template>
	<view>
		<view class="userHeader">
			<image class="avatar" src="../../static/me/defaultAvatar.png" mode=""></image>
			<view class="lable">
				点击授权
			</view>
		</view>
		<view class="list">
			<view @click="goChangSf(item)" class="item" v-for="(item,index) in list" :key="index">
				<image class="leftIcon" :src="item.leftIcon" mode=""></image>
				<view class="text">{{item.text}}</view>
				<image class="rightIcon" src="../../static/me/more.png" mode=""></image>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [
					{
						leftIcon: "../../static/me/list1.png",
						text: '身份切换',
						url: '/pages/me/changSf/changSf'
					},
					{
						leftIcon: "../../static/me/list2.png",
						text: '我的钱包',
						url: '/pages/me/wallet/wallet'
					},
					{
						leftIcon: "../../static/me/list3.png",
						text: '寄存点管理',
						
					},
					{
						leftIcon: "../../static/me/list4.png",
						text: '历史订单',
						
					},
					{
						leftIcon: "../../static/me/list5.png",
						text: '关于我们',
						url: '/pages/me/aboutMe/aboutMe'
					}	
				]
			}
		},
		methods: {
			goChangSf(item) {
				console.log('路由跳转',item)
				uni.navigateTo({
					url: item.url
				})
			}
		}
	}
</script>

<style lang="less">
	page {
		background-color: #F3F3F3;
	}
	.userHeader {
		background-image: url(../../static/me/bg.png);
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
	.list {
		padding: 0 28rpx;
		.item {
			display: flex;
			height: 106rpx;
			align-items: center;
			border-bottom: 1px solid #E3E8EE;
			.leftIcon {
				width: 38rpx;
				height: 38rpx;
			}
			.text {
				flex: 1;
				margin-left: 16rpx;
				font-size: 26rpx;
				color: #333333;
			}
			.rightIcon {
				width: 14rpx;
				height: 22rpx;
				margin-left: auto;
			}
		}
	}
	
</style>
