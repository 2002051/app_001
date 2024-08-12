<template>
	<!-- 登录组件 -->
	<view class="loginForm">
		<view class="head">
			<text>登录</text>
			<uni-icons type="closeempty" @click="handleClick"></uni-icons>
		</view>

		<view class="form">

		</view>

		<view class="other">

		</view>
	</view>
	<!-- 黑色遮罩层 -->
	<view class="curtain" @click="handleClick">

	</view>

</template>

<script setup>
	import {
		defineEmits
	} from 'vue';

	const emit = defineEmits(['doClose']);
	
	const handleClick = () => {
	  emit('doClose', 'Hello from child'); // 触发事件并传递数据
	};
</script>

<style lang="scss" scoped>
	.loginForm {
		position: fixed;
		top: 280rpx;
		left: 110rpx;
		width: 500rpx;
		height: 300rpx;
		background-color: white;
		z-index: 6;
		border-radius: 15rpx;

		.head {
			margin-top: 5rpx;
			margin-right: 10rpx;
			display: flex;
			width: 55%;
			margin-left: auto;
			justify-content: space-between;
			align-items: center;
		}
	}

	.curtain {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background-color: rgba(0, 0, 0, 0.5); // 半透明遮罩层
		display: flex;
		justify-content: center;
		align-items: center;
		z-index: 5; // 确保遮罩层在最上层
	}
</style>