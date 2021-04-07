<template>
	<view>
		<view class="form">
			<view class="title">
				<view class="block"></view>
				<view class="lable">寄出行李</view>
				<view class="right">
					<view class="item">寄存</view>
					<view class="item act">寄出</view>
				</view>
			</view>
			<view class="inputView">
				<picker @cancel="sendFold = true" @click="sendFold = !sendFold" mode="selector" :range="sendRange" @change="">
					<view class="item">
						<view class="left">寄出地点</view>
						<input :disabled="true" placeholder="您寄出行李的地点" class="input" type="text" value="" />
						<image :class="sendFold ? '' : 'imageRotate'" class="image" src="../../static/index/fold.png" mode=""></image>
					</view>
				</picker>
				
				<picker @cancel="sendFold = true" @click="sendFold = !sendFold" mode="selector" :range="sendRange" @change="">
					<view class="item">
						<view class="left">寄出时间</view>
						<input :disabled="true" placeholder="您将行李寄出的时间" class="input" type="text" value="" />
						<image :class="sendFold ? '' : 'imageRotate'" class="image" src="../../static/index/fold.png" mode=""></image>
					</view>
				</picker>
			</view>
		</view>
		
		<view class="form">
			<view class="title">
				<view class="block"></view>
				<view class="lable">领回行李</view>
			</view>
			<view class="inputView">
				<picker @cancel="sendFold = true" @click="sendFold = !sendFold" mode="selector" :range="sendRange" @change="">
					<view class="item">
						<view class="left">领回地点</view>
						<input :disabled="true" placeholder="您寄出行李的地点" class="input" type="text" value="" />
						<!-- <view class="right">456</view> -->
						<image :class="sendFold ? '' : 'imageRotate'" class="image" src="../../static/index/fold.png" mode=""></image>
					</view>
				</picker>
				
				<picker @cancel="sendFold = true" @click="sendFold = !sendFold" mode="selector" :range="sendRange" @change="">
					<view class="item">
						<view class="left">领回时间</view>
						<input :disabled="true" placeholder="您将行李寄出的时间" class="input" type="text" value="" />
						<!-- <view class="right">456</view> -->
						<image :class="sendFold ? '' : 'imageRotate'" class="image" src="../../static/index/fold.png" mode=""></image>
					</view>
				</picker>
			</view>
		</view>
		
		<view class="form">
			<view class="title">
				<view class="block"></view>
				<view class="lable">行李信息</view>
				<view @click="seeHelp" class="help">
					<image class="helpIcon" src="../../static/index/help.png" mode=""></image>
					<view class="label">行李规则</view>
				</view>
			</view>
			<view class="inputView">
				<view class="helpItem">
					<view class="top">
						<view class="l">行李件数</view>
						<view class="r">
							<view class="ctrView">
								<image class="icon" src="../../static/index/less.png" mode=""></image>
							</view>
							<view class="num">{{number}}</view>
							<view class="ctrView">
								<image class="icon" src="../../static/index/add.png" mode=""></image>							
							</view>
							<view class="num">件</view>
						</view>
					</view>
					<view class="bottom">
						单件行李箱大小上限为32寸
					</view>
				</view>
				
				<view class="helpItem">
					<view class="topView">
						<view class="left">
							<view class="t">行李照片或寄存凭证</view>
							<view class="b">最多上传6张</view>
						</view>
						<view class="upload">
							<image class="uploadIcon" src="../../static/index/upload.png" mode=""></image>
						</view>
					</view>
				</view>
				
			</view>
		</view>
		
		<view class="form">
			<view class="title">
				<view class="block"></view>
				<view class="lable">添加旅客信息</view>
			</view>
			<view class="inputView">
				<view class="userMsg">
					<view class="left">联系人</view>
					<view class="right">
						<input class="input" placeholder-class="commonPlaceHolder" type="text" placeholder="请填写酒店入住人姓名" value="" />
					</view>
				</view>	
				
				<view class="userMsg">
					<view class="left">手机号</view>
					<view class="right">
						<input class="input" placeholder-class="commonPlaceHolder" placeholder="请填写手机号" value="" />
						<view class="msg">
							<image class="msgIcon" src="../../static/index/msg.png" mode=""></image>
							<view class="txt">
								服务过程中因手机号填写错误导致配送无法完成需自行承担
							</view>
						</view>
					</view>
				</view>
				
				<view class="userMsg">
					<view class="left">其他手机号</view>
					<view class="right">
						<input placeholder-class="commonPlaceHolder" placeholder="请填写其他紧急联系" class="input" type="text" value="" />
					</view>
				</view>
				
				<view class="userMsg">
					<view class="left">车次</view>
					<view class="right">
						<input placeholder-class="commonPlaceHolder" placeholder="选填车次号" class="input" type="text" value="" />
					</view>
				</view>
			</view>
		</view>
		
		<view class="bottomCtr">
			<view class="msg">若有特殊需求请联系客服</view>
			<view class="btnView">
				<view class="price">
					<view class="l">￥</view>
					<view class="r">49.00</view>
				</view>
				<view @click="goPay" class="btn">
					立即下单
				</view>
			</view>
		</view>
		
		<view class="service">
			<image class='serviceIcon' src="../../static/index/service.png" mode=""></image>
			<view class="serviceItem">
				<view class="serviceTitle">
					<view class="circle"></view>
				    <view class="lable">退房后行李很尴尬</view>
					<image class="image" src="../../static/index/fold.png" mode=""></image>
				</view>
			</view>
			<view class="serviceItem">
				<view class="serviceTitle">
					<view class="circle"></view>
				    <view class="lable">行李多又重</view>
					<image class="image" src="../../static/index/fold.png" mode=""></image>
				</view>
			</view>
			<view class="serviceItem">
				<view class="serviceTitle">
					<view class="circle"></view>
				    <view class="lable">拥堵的地面交通</view>
					<image class="image" src="../../static/index/fold.png" mode=""></image>
				</view>
			</view>
		</view>
		
		<view class="end">
			<image class="endImage" src="../../static/index/end.png" mode=""></image>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				//寄出地点
				sendRange: [],
				sendFold: true,
				//行李件数
				number: 1
			}
		},
		methods: {
			seeHelp() {
				uni.navigateTo({
					url: '../../pages/index/rule/rule'
				})
			},
			goPay() {
				uni.navigateTo({
					url: '../../pages/index/readyPay/readyPay'
				})
			}
		}
	}
</script>

<style lang="less">
	.form {
		background-color: #FFFFFF;
		border-radius: 12rpx;
		overflow: hidden;
		margin-top: 20rpx;
		.title {
			display: flex;
			height: 90rpx;
			align-items: center;
			.block {
				width: 8rpx;
				height: 36rpx;
				background-color: #28A032;
			}
			.lable {
				margin-left: 24rpx;
				color: #222222;
				font-size: 32rpx;
				font-weight: bold;
			}
			.help {
				display: flex;
				align-items: center;
				margin-right: 24rpx;
				margin-left: auto;
				.helpIcon {
					width: 28rpx;
					height: 28rpx;
				}
				.label {
					margin-left: 12rpx;
					font-size: 28rpx;
					color: #28A032;
					font-weight: bold;
				}
			}
			.right {
				margin-right: 32rpx;
				margin-left: auto;
				display: flex;
				align-items: center;
				border-radius: 100px;
				overflow: hidden;
				width: 190rpx;
				background-color: #F3F3F3;
				.item {
					flex: 1;
					background-color: #F3F3F3;
					height: 48rpx;
					display: flex;
					align-items: center;
					justify-content: center;
					font-size: 26rpx;
					color: #666666;
				}
				.act {
					color: #FFFFFF;
					background-color: #28A032;
					border-radius: 100px;
				}
			}
		}
		.inputView {
			padding: 0 30rpx;
			.item {
				display: flex;
				align-items: center;
				height: 82rpx;
				border-top: 1px solid #F7F8FA;
				.left {
					font-size: 28rpx;
					color: #999999;
					font-weight: bold;
					
				}
				.input {
					font-size: 28rpx;
					color: #EBEBEB;
					width: 224rpx;
					height: 40rpx;
					font-weight: bold;
					line-height: 40rpx;
					margin-left: 60rpx;
					flex: 1;
				}
				.image {
					width: 16rpx;
					height: 32rpx;
					transition: 0.3s;
				}
				.imageRotate {
					transform: rotate(90deg);
					width: 16rpx;
					height: 32rpx;
				}
			}
		}
		
	}
	.service {
		margin-top: 20rpx;
		overflow: hidden;
		border-radius: 12rpx;
		background-color: #FFFFFF;
		.serviceIcon {
			width: 382rpx;
			height: 106rpx;
			display: block;
			margin: 0 auto;
			margin-top: 32rpx;
			margin-bottom: 22rpx;
		}
		.serviceItem {
			border: 1px solid #EBEBEB;
			.serviceTitle {
				display: flex;
				align-items: center;
				padding: 0 20rpx;
				height: 100rpx;
				.circle {
					width: 12rpx;
					height: 12rpx;
					border-radius: 12rpx;
					background-color: #28A032;
				}
				.lable {
					font-size: 28rpx;
					margin-left: 16rpx;
					color: #222222;
				}
				.image {
					width: 16rpx;
					height: 32rpx;
					margin-left: auto;
				}
				
			}
		}
	}
	.end {
		margin-top: 20rpx;
		margin-bottom: 60rpx;
		.endImage {
			width: 694rpx;
			height: 172rpx;
			display: block;
			margin: 0 auto;
		}
	}
	.helpItem {
		border-top: 1px solid #F7F8FA;
		padding-bottom: 22rpx;
		.top {
			display: flex;
			align-items: center;
			.l {
				font-size: 28rpx;
				color: #222222;
				font-weight: bold;
			}
			.r {
				margin-left: auto;	
				display: flex;
				align-items: center;
				.ctrView {
					padding: 22rpx;
					.icon {
						width: 32rpx;
						height: 32rpx;
					}
				}
				.num {
					font-size: 28rpx;
					color: #222222;
				}
			}
		}
		.bottom {
			font-size: 24rpx;
			color: #999999;
		}
		.topView {
			display: flex;
			align-items: center;
			.left {
				.t {
					font-size: 28rpx;
					color: #999999;
					font-weight: bold;
				}
				.b {
					margin-top: 12rpx;
					font-size: 24rpx;
					color: #999999;
				}
			}
			.upload {
				padding: 28rpx;
				margin-right: 38rpx;
				margin-left: auto;
				.uploadIcon {
					width: 80rpx;
					height: 80rpx;
					
				}
			}
		}
	}
	.userMsg {
		display: flex;
		padding: 20rpx 30rpx;
		border-top: 1px solid #F7F8FA;
		.left {
			font-size: 28rpx;
			font-weight: bold;
			color: #999999;
			width: 200rpx;
		}
		.right {
			flex: 1;
			height: 100%;
			.input {
				height: 100%;
				font-size: 28rpx;
			}
			.msg {
				display: flex;
				margin-top: 16rpx;
				.msgIcon {
					width: 24rpx;
					height: 24rpx;
					margin-right: 10rpx;
				}
				.txt {
					flex: 1;
					font-size: 24rpx;
					color: #FD6A28;
					font-weight: bold;
				}
			}
		}
	}
	.bottomCtr {
		position: fixed;
		bottom: 0;
		left: 0;
		right: 0;
		z-index: 999;
		background-color: #FFFFFF;
		.msg {
			height: 48rpx;
			background-color: rgba(255,119,1,0.1);
			line-height: 48rpx;
			text-align: center;
			color: #FD6A28;
			font-size: 24rpx;
		}
		.btnView {
			height: 98rpx;
			display: flex;
			.price {
				margin-left: 52rpx;
				display: flex;
				align-items: center;
				color: #FD6A28;
				.l {
					font-size: 32rpx;
				}
				.r {
					font-size: 44rpx;
					margin-left: 6rpx;
				}
			}
			.btn {
				background-color: #FF7701;
				margin-left: auto;
				width: 300rpx;
				color: #FFFFFF;
				line-height: 98rpx;
				text-align: center;
			}
		}
	}
</style>
