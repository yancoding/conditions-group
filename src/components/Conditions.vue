<template>
	<div>
		<div v-for="(condition,index) in initContitions" :key="condition.id">
			<el-row>
				<el-col :span="2">
					<div class="box-1"></div>
				</el-col>
				<el-col :span="21" class="grid-content">
					<ConditionItem :conditionItem="condition.conditionItem"/>
				</el-col>
				<el-col :span="1" class="grid-content">
					<el-button type="text" icon="el-icon-delete" circle size="mini" @click="removeConditionItem(index)"></el-button>
				</el-col>
			</el-row>
		</div>
		<el-row>
			<el-col :span="2" class>
				<div class="box-2"></div>
			</el-col>
			<el-col :span="22" class="grid-content">
				<el-button icon="el-icon-plus" plain circle size="mini" @click="addConditionItem"></el-button>
			</el-col>
		</el-row>
		
	</div>
</template>

<script>
	import ConditionItem from './ConditionItem.vue'

	export default {
		name: 'Conditions',
		data(){
			return {
				initContitions: this.conditions,
				nextId: this.conditions.length + 1
			}
		},
		props: {
			conditions: {
				type: Array,
				default: () => [{
					id: 1,
					conditionItem: [{
						options: [{id:1,value: 'a',label: 'A'},{id:2,value: 'b',label: 'B'},{id:3,value: 'c',label: 'C'}],
						value: ''
					},{
						options: [{id:1,value: 'a',label: 'A'},{id:2,value: 'b',label: 'B'},{id:3,value: 'c',label: 'C'}],
						value: ''
					},{value: ''}]
				},{
					id: 2,
					conditionItem: [{
						options: [{id:1,value: 'a',label: 'A'},{id:2,value: 'b',label: 'B'},{id:3,value: 'c',label: 'C'}],
						value: ''
					},{
						options: [{id:1,value: 'a',label: 'A'},{id:2,value: 'b',label: 'B'},{id:3,value: 'c',label: 'C'}],
						value: ''
					},{value: ''}]
				}]
			}
		},
		components: {
			ConditionItem
		},
		methods: {
			addConditionItem(){
				let pushItem = {
					id: 1,
					conditionItem: [{
						options: [{id:1,value: 'a',label: 'A'},{id:2,value: 'b',label: 'B'},{id:3,value: 'c',label: 'C'}],
						value: ''
					},{
						options: [{id:1,value: 'a',label: 'A'},{id:2,value: 'b',label: 'B'},{id:3,value: 'c',label: 'C'}],
						value: ''
					},{value: ''}]
				};
				pushItem.id = this.nextId++;
				this.initContitions.push(pushItem);
			},
			removeConditionItem(index){
				this.initContitions.splice(index,1);
			}
		}
	}
</script>

<style>
	.box-1{
		width: 30px;
		height: 47px;
		border-top: 1px solid #DCDFE6;
		border-left: 1px solid #DCDFE6;
		position: relative;
		top: 23px;
	}
	.box-2{
		width: 30px;
		height: 46px;
		border-top: 1px solid #DCDFE6;
		position: relative;
		top: 23px;
	}
	.grid-content{
		margin: 10px 0;
	}
	.line-text-content{
		text-align: center;
	}
	.line-text-content:before{
		content: '';
		display: block;
		border-top: 1px dashed grey;
		position: relative;
		top: 12px;
	}
	.line-text{
		color: grey;
		background-color: #fff;
		position: relative;
		padding: 0 10px;
	}
</style>