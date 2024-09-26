<template>
	<!-- 登录组件 -->
	<view class="loginForm" v-show="isLogin">
		<view class="head">
			<text>登录</text>
			<uni-icons type="closeempty" @click="handleClick"></uni-icons>
		</view>

		<view class="form">
			<input type="text" :value="loginForm.username" placeholder="请输入用户名" />
			<input type="password" :value="loginForm.password" placeholder="请输入密码" />
			<button>点击登录</button>
		</view>

		<view class="other" @click="ChangeForm">
			没有账号？点击注册
		</view>
	</view>

	<view class="registerForm" v-show="!isLogin">
		<view class="head">
			<text>注册</text>
			<uni-icons type="closeempty" @click="handleClick"></uni-icons>
		</view>
		<view class="form">
			<input type="text" :value="registerForm.mobile" placeholder="请输入手机号" />
			<input type="text" :value="registerForm.username" placeholder="请输入用户名" />
			<input type="password" :value="registerForm.password" placeholder="请输入密码" />
			<button @click="doRegister">点击注册</button>

		</view>
		<view class="other" @click="ChangeForm">
			我有账号，我要登录
		</view>


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
	const isLogin = ref(true);
	const loginForm = ref({
		username: "",
		password: ""
	})
	const registerForm = ref({
		mobile: "",
		username: "",
		password: ""
	})

	const handleClick = () => {
		emit('doClose', 'Hello from child'); // 触发事件并传递数据
	};

	const ChangeForm = () => {
		isLogin.value = !isLogin.value
	};
	const doRegister = () => {
		
	};
	const doLogin = () => {
		
	};
</script>

<style lang="scss" scoped>
	.loginForm {
		.other {
			margin-top: 10rpx;
			text-align: center;
			font-size: 25rpx;
		}

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

		.form {
			margin: 0rpx 20rpx;

			input {
				margin-top: 10rpx;
				margin-bottom: 10rpx;
				border: solid 1rpx #d0d1c7;
				border-radius: 10rpx;
			}

			button {
				background-color: #dbe1e8;
				margin-top: 20rpx;
				height: 50rpx;
				width: 80%;
				font-size: 30rpx;
				line-height: 50rpx;
				text-align: center;
			}
		}
	}


	.registerForm {
		.other {
			margin-top: 10rpx;
			text-align: center;
			font-size: 25rpx;
		}

		position: fixed;
		top: 280rpx;
		left: 110rpx;
		width: 500rpx;
		height: 350rpx;
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

		.form {
			margin: 0rpx 20rpx;

			input {
				margin-top: 10rpx;
				margin-bottom: 10rpx;
				border: solid 1rpx #d0d1c7;
				border-radius: 10rpx;
			}

			button {
				background-color: #dbe1e8;
				margin-top: 20rpx;
				height: 50rpx;
				width: 80%;
				font-size: 30rpx;
				line-height: 50rpx;
				text-align: center;
			}
		}
	}


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