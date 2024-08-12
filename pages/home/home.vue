<template>
<login_form @doClose="Do" v-if="isShowLoginForm">
	
</login_form>

</template>

<script setup>
import { ref } from 'vue';

const isShowLoginForm = ref(true)

function Do(){
isShowLoginForm.value = !isShowLoginForm.value
}
</script>

<style lang="scss">

</style>


