<template>
	<view class="headbox">
		<view class="head">
			<view class="headItem" v-if="isSearching">
				<view class="left">
				
						<uni-icons type="back" size="25" @click="doGoBack"></uni-icons>
						<text>2144项</text>
				
				</view>
				<view class="btn">
					<uni-icons type="search" size="25" @click="doClickSearch"></uni-icons>
					<uni-icons type="upload" size="25" click="doUpload"></uni-icons>

				</view>

			</view>
			<view class="headItem" v-if="!isSearching">
				<view class="search"><input type="text" /></view>
				<view class="close" @click="doClickSearch">
					取消
				</view>
			</view>

		</view>
	</view>

	<!-- 相册页面 -->
	<view class="box">
		<view class="pic"
			v-for="(item, index) in [1, 2, 3, 4, 5, 6, 7, 8,4, 5, 6, 7, 8,4, 5, 6, 7, 8,4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14]"
			:key="index">
			<!-- 图片区域 -->
			<image src="../../static/demo.jpg" mode="" @click="gotoDetail"></image>
		</view>
	</view>
</template>

<script setup>
	import {
		ref
	} from 'vue';
	const isSearching = ref(true)
	// 获取系统信息
	const systemInfo = uni.getSystemInfoSync();
	const statusBarHeight = systemInfo.statusBarHeight; // 获取状态栏高度

	// 固定头部的高度
	const topBarHeight = 80; // 根据实际情况调整
	const marginTop = topBarHeight + statusBarHeight + 'px'; // 总高度

	// 将 `marginTop` 值存储到一个变量中，以便在样式中使用
	const marginTopValue = marginTop;

	const doClickSearch = () => {
		isSearching.value = !isSearching.value
	}
	const doUpload = () => {
		console.log("点击上传")
	}
	const doGoBack = ()=>{
		uni.navigateBack()
	}
	const detail = ()=>{
		
	}
	const gotoDetail = ()=>{
		uni.navigateTo({
			url:"/pages/pgdetail/pgdetail"
		})
	}
</script>

<style lang="scss">
	.headbox {
		position: relative;
		overflow: hidden; // 隐藏溢出的内容

		.head {
			position: fixed; // 固定头部
			top: 0; // 使用固定值，避免使用 env()
			left: 0;
			width: 100%;
			height: 100rpx;
			background-color: #fff; // 确保背景色
			z-index: 1000; // 确保在内容上方

			.headItem {
				display: flex;
				padding: 30rpx;
				justify-content: space-between;
				align-items: center; // 确保垂直居中
				.left{
					display: flex;
					justify-content: center;
					align-items: center;
				}
				.search {
					display: flex;
					justify-content: center;
					align-items: center;

					input {
						width: 550rpx;
						border: 1px solid #d5d5d5;
					}

					.close {}
				}
			}
		}
	}

	.box {
		// padding-top: 100rpx; // 给固定头部下面的内容留出空间
		// width: 750rpx;
		// background-color: red;
		display: flex; // 确保使用 flex 布局
		flex-wrap: wrap; // 如果需要换行

		.pic {
			padding-top: 10rpx;
			width: 230rpx;
			height: 200rpx;
			margin-left: 10rpx;
			display: flex; // 使 .pic 内部元素也使用 flex 布局

			image {
				width: 100%;
				height: 100%;
			}
		}
	}
</style>