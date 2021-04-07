<template>
	<view>
		<view class="header">
			<view class="txt">账户余额</view>
			<view class="price">{{price}}</view>
		</view>
		
		<view class="list">
			<list-item class="list-item" v-for="(item,index) in walletList" :key="index">
				<view slot="left" class="left">{{item.label}}</view>
				<view slot="center" class="center"></view>
				<!-- <view slot="right" class="right">右</view> -->
				<image slot="right" class="right" :src="item.icon" mode=""></image>
			</list-item>
		</view>
	</view>
</template>

<script>
	import ListItem from '../../../components/listItem/ListItem.vue'
	export default {
		components: {
			ListItem
		},
		data() {
			return {
				price: 100,
				walletList: [
					{
						label: '充值',
						icon: '../../../static/index/fold.png'
					},
					{
						label: '提现',
						icon: '../../../static/index/fold.png'
					},
					{
						label: '余额明细',
						icon: '../../../static/index/fold.png'
					}
				]
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="less">
	.header {
		padding: 48rpx 40rpx;
		color: #FFFFFF;
		height: 232rpx;
		background: linear-gradient(90deg,#28A032 0%, #50C414 100%);
		.txt {
			font-size: 32rpx;
		}
		.price {
			margin-top: 32rpx;
			font-size: 50rpx;
			font-weight: bold;
		}
	}
	.list {
		background-color: #FFFFFF;
		margin-top: 14rpx;
		.list-item {
			&:last-child {
				border-bottom: none;
			}
			.left {
				color: #222222;
				font-weight: bold;
				font-size: 32rpx;
			}
			.right {
				width: 16rpx;
				height: 32rpx;
			}
		}
	}
	
</style>
