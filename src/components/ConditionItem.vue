<template>
	<el-row :gutter="10">
		<el-col :span="8">
			<BaseSelect :select="initConditionItem[0]"/>
		</el-col>
		<el-col :span="8">
			<BaseSelect :select="initConditionItem[1]"/>
		</el-col>
		<el-col :span="8">
			<BaseInputText :input="initConditionItem[2]"/>
		</el-col>
	</el-row>
</template>

<script>
	import BaseSelect from './BaseSelect.vue'
	import BaseInputText from './BaseInputText.vue'

	export default {
		name: 'ConditionItem',
		data(){
			return {
				initConditionItem: this.conditionItem
			}
		},
		props: {
			conditionItem: {
				type: Array,
				default: () => [{
					options: [{id:1,value: 'a',label: 'A'},{id:2,value: 'b',label: 'B'},{id:3,value: 'c',label: 'C'}],
					value: ''
				},{
					options: [{id:1,value: 'a',label: 'A'},{id:2,value: 'b',label: 'B'},{id:3,value: 'c',label: 'C'}],
					value: ''
				},{value: ''}]	
			}
		},
		components: {
			BaseSelect,
			BaseInputText
		}
	}
</script>

<style>
	
</style>