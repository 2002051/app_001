<template>
	<!-- 登录组件 -->
	<view class="loginForm">
		
	</view>



	<!-- 黑色遮罩层 -->
	<view class="curtain" @click="handleClick">

	</view>

<view class="tools">
	<uni-icons type="add" size="30"></uni-icons>
	<!-- 添加 -->
	
</view>
</template>

<script setup>
	import {
		ref
	} from 'vue';

	import {
		defineEmits
	} from 'vue';

	const emit = defineEmits(['doClose']);
	
	
	const handleClick = () => {
		emit('doClose', 'Hello from child'); // 触发事件并传递数据
	};


</script>

<style lang="scss" scoped>



	.curtain {
		font-size: 150rpx;
		color: pink;
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background-color: rgba(0, 0, 0, 0.5); // 半透明遮罩层
		// background-color:#; // 半透明遮罩层
		display: flex;
		justify-content: center;
		align-items: center;
		z-index: 5; // 确保遮罩层在最上层
	}
</style>