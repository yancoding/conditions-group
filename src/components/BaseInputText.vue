<template>
	<el-input size="mini" v-model="initInput.value"></el-input>
</template>

<script>
	export default {
		name: 'BaseInputText',
		data(){
			return {
				initInput: this.input
			}
		},
		props: {
			input: {
				type: Object,
				default: () => ({value: ''}) 
			}
		}
	}
</script>

<style>
	
</style>