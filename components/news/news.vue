<template>
	<!-- 公告区域 -->
	<view class="notice">
		<view class="left">
			<!-- <uni-icons type="sound-filled" size="20" color="#28B389"></uni-icons> -->
			<uni-icons type="sound-filled" size="20"></uni-icons>
			<text class="text">公告</text>
		</view>
		<view class="center">
			<swiper vertical autoplay interval="1500" duration="300" circular>
				<swiper-item v-for="item in noticeList" :key="item._id">
					<navigator url="/pages/notice/noticedetail"> {{item.title}}</navigator>
				</swiper-item>
			</swiper>
		</view>
		<view class="right">
			<uni-icons type="right" size="16" color="#333"></uni-icons>
		</view>
	</view>

</template>

<script setup>
	import {
		ref
	} from 'vue';
	const noticeList = ref([{
		id: 1,
		title: "123",
	}, {
		id: 2,
		title: "123",
	}, {
		id: 3,
		title: "123",
	}])
</script>

<style scoped lang="scss">
	.notice {
		width: 690rpx;
		height: 80rpx;
		background-color: #ebebeb;
		margin: 0 auto;
		display: flex;
		border-radius: 80rpx;
		line-height: 80rpx;

		.left {
			width: 140rpx;
			display: flex;
			align-items: center;
			justify-content: center;

			:deep() {
				.uni-icons {
					color: #28B389;
				}
			}


			.text {
				color: #28B389;
				font-weight: 600;
				font-size: 28rpx;
			}
		}

		.right {
			width: 70rpx;
			display: flex;
			align-items: center;
			justify-content: center;
		}

		.center {
			flex: 1;

			swiper {
				height: 100%; // 高度继承父级

				swiper-item {
					height: 100%;
					font-size: 30rpx;
					//  超出一定长度的内容,用...表示
					overflow: hidden;
					text-overflow: ellipsis;
				}
			}

		}
	}
</style>