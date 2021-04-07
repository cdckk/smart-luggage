<template>
	<view class="paddingView">
		<view class="sticky">
			<view class="searchBox">
				<image class="searchIcon" src="../../static/find/search.png" mode=""></image>
				<input :placeholder-class="placeholder" class="input" placeholder="根据取件码搜索订单" type="text" value="" />
				<view class="searchButton">搜索</view>
			</view>
		</view>
		
		<view class="noList" v-if="list.length == 0">
			<image class="noListIcon" src="../../static/find/notList.png" mode=""></image>
		</view>
		
		<view class="list" v-else>
			<view class="item" v-for="(item,index) in 20" :key="index">
				<view class="it">
					<view class="left">寄件人：</view>
					<view class="right">张三</view>
				</view>
				<view class="it">
					<view class="left">手机号：</view>
					<view class="right">1864121234</view>
				</view>
				<view class="it">
					<view class="left">寄存地点：</view>
					<view class="right">新桥机场</view>
				</view>
				<view class="it">
					<view class="left">取件码：</view>
					<view class="right origin">2367</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: []
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
	.paddingView {
		.sticky {
			position: sticky;
			top: 87rpx;
			padding: 40rpx 28rpx;
			background-color: #F3F3F3;
			.searchBox {
				overflow: hidden;
				border-radius: 12rpx;
				display: flex;
				align-items: center;
				background-color: #EBEBEB;
				.searchIcon {
					width: 36rpx;
					height: 36rpx;
					margin-left: 28rpx;
				}
				.input {
					
					flex: 1;
					width: 252rpx;
					height: 40rpx;
					font-size: 28rpx;
					margin: 0 18rpx;
				}
				.placeholder {
					color: #BEBEBE;
				}
				.searchButton {
					background: linear-gradient(90deg,#28A032 0%, #50C414 100%);
					color: #FFFFFF;
					margin-left: auto;
					width: 120rpx;
					height: 70rpx;
					font-size: 32rpx;
					display: flex;
					justify-content: center;
					align-items: center;
				}
			}
		
		}
		.list {
			margin-top: 40rpx;
			.item {
				background-color: #FFFFFF;
				border-radius: 12rpx;
				padding: 24rpx 40rpx 0;
				.it {
					display: flex;
					align-items: center;
					font-weight: bold;
					.left {
						font-size: 28rpx;
						color: #666666;
					}
					.right {
						font-size: 28rpx;
						color: #222222;
						margin-left: 18rpx;
					}
					.origin {
						color: #FD6A28;
					}
				}
			}
		}
		.noList {
			.noListIcon {
				width: 280rpx;
				height: 340rpx;
				position: absolute;
				left: 0;
				right: 0;
				top: 0;
				bottom: 0;
				margin: auto;
			}
		}
	}
</style>
