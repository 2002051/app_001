<template>
	<view class="body">
		
		<login_form @doClose="Do" v-if="isShowLoginForm"></login_form>
		<view class="news">
			<news></news>
		</view>
		<view class="navigatelast">
			<view class="navigate" style="background-color: #f2ffb5;" v-for="(item,index) in navList" :key="item.id">
				{{item.title}}
			</view>
		</view>

		<view class="albumlist">
			<view class="albumitem" v-for="(item,index) in albumList" :key="item.id">
				<photoalbum></photoalbum>
			</view>
		</view>
	</view>

<view class="tools">
	<uni-icons type="plus" size="30"></uni-icons>
	<!-- 添加 -->
</view>


</template>

<script setup>
	import {
		ref
	} from 'vue';

	const isShowLoginForm = ref(true)
	const navList = ref([{
		id: 1,
		title: "旅游"
	}, {
		id: 2,
		title: "美食"
	}, {
		id: 3,
		title: "游戏"
	}, {
		id: 4,
		title: "家居"
	}, {
		id: 5,
		title: "家居"
	}, {
		id: 6,
		title: "家居"
	}, {
		id: 7,
		title: "家居"
	},])
	const albumList = ref([{
		id: 1,
		title: "测试相册1"
	}, {
		id: 2,
		title: "测试相册2"
	}, {
		id: 3,
		title: "测试相册3"
	}, {
		id: 4,
		title: "测试相册4"
	}, {
		id: 4,
		title: "测试相册4"
	}])


	function Do() {
		isShowLoginForm.value = !isShowLoginForm.value
	}
</script>

<style lang="scss">
	.body {
		position: relative;
		// background-color: #cbcbcb;
		width: 100%;
		height: 100vh;

		/* 或者使用其他适当的高度 */
		.news {
			padding-top: 30rpx;
		}

		.navigatelast {
			display: flex;
			margin-top: 30rpx;

			.navigate {
				margin-left: 30rpx;
				// background-color: #ff7f2a;
				width: 80rpx;
				height: 40rpx;
				text-align: center;
			}
		}

		.albumlist {
			margin-top: 30rpx;
			margin-left: 30rpx;
			display: flex;
			justify-items: center;
			align-items: center;
			flex-wrap: wrap;
			.albumitem {
				// background-color: red;
			}

		}
	}
	.tools{
			color:black;
			position: fixed; /* 固定定位 */
		    bottom: 200rpx; /* 距离底部 0 像素 */
		    right: 30rpx; /* 距离左侧 0 像素 */
		    padding: 5px; /* 可以调整内边距 */
		    background-color: rgba(255, 255, 255, 0.8); /* 透明背景颜色，防止图标与背景混合 */
		    border-radius: 8px; /* 圆角 */
		    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2); /* 阴影效果 */
	
	}
</style>