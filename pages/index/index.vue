<template>
	<view class="paddingView">
		<image class="bannerPic" src="../../static/index/banner.png" mode=""></image>
		<send></send>
	</view>
</template>

<script>
	import send from '../../components/index/send.vue'
	export default {
		components: {
			send
		},
		data() {
			return {
				
			}
		},
		onLoad() {

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
		padding: 28rpx;
	}
	.bannerPic {
		width: 694rpx;
		height: 260rpx;
	}
</style>
