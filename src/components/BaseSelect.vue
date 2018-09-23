<template>
	<el-select size="mini" v-model="initSelect.value">
		<el-option v-for="option in select.options" :key="option.id" :value="option.value" :label="option.label"></el-option>
	</el-select>
</template>

<script>
	export default {
		name: 'BaseSelect',
		data(){
			return {
				initSelect: this.select
			}
		},
		props: {
			select: {
				type: Object,
				default: () => ({
					options: [{id:1,value: 'a',label: 'A'},{id:2,value: 'b',label: 'B'},{id:3,value: 'c',label: 'C'}],
					value: ''
				})
			}
		}
	}
</script>
<style>
	
</style>