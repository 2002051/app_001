<template>
	<view class="box" @click="gotoAlbum">
		<view class="pic">
			<image src="../../static/demo.jpg" mode="aspectFit"></image>
		</view>
		<view class="text">
			这是xxxx相册 这是xxxx相册
		</view>
	</view>
</template>

<script setup>
import { ref } from 'vue';

	function gotoAlbum() {
		uni.navigateTo({
			url: '/pages/album/album'
		})
	}
</script>

<style lang="scss" scoped>
	.box {
		width: 345rpx;
		height: 240rpx;

		.pic {
			width: 100%;
			height: 80%;

			image {
				width: 100%;
				height: 100%;
			}
		}

		.text {
			white-space: nowrap;
			/* 防止文本换行 */
			overflow: hidden;
			/* 超出容器部分隐藏 */
			text-overflow: ellipsis;
			/* 超出部分用省略号表示 */
			width: 100%;
			height: 20%;
			text-align: center;
		}

	}
</style>