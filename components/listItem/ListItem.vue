<template>
	<view class="list">
		<view class="list-item">
			<view class="left">
				<slot name="left"></slot>
			</view>
			<view class="center">
				<slot name="center"></slot>
			</view>
			<view class="right">
				<slot name="right"></slot>
			</view>
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
			
		}
	}
</script>

<style lang="less" scoped>
	.list {
		padding: 0 28rpx;
		.list-item {
			display: flex;
			align-items: center;
			height: 104rpx;
			border-bottom: 1px solid #E3E8EE;
			.center {
				flex: 1;
				margin-left: 16rpx;
			}
			.right {
				margin-right: auto;
			}
		}
	}
</style>
