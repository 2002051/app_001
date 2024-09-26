<template>
	<button @click="doShow" v-if="!showing">点击开始直播</button>
	<button @click="doShow" v-if="showing">点击关闭直播</button>
	
</template>

<script setup>
import { ref } from 'vue';

const showing = ref(false)


const doShow = (res)=>{
	showing.value = !showing.value
	if(!!showing.value){
		startStream();
	}
}
const startStream = (x)=>{
	const cameraContext = uni.createCameraContext();
	cameraContext.startRecord({
	        success: (res) => {
	          console.log('录制成功', res);
	          // 处理录制的视频流
	        },
	        fail: (err) => {
	          console.error('录制失败', err);
	        }
	      });

}


</script>

<style lang="scss">

</style>


