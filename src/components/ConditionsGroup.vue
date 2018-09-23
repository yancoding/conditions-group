<template>
	<div class="conditionsgroup">
		<div v-for="(conditionsGroupitem,index) in initConditionsGroup" :key="conditionsGroupitem.id">
			<el-row class="center-container">
				<el-col :span="4" class="center-content">
					<el-button icon="el-icon-minus" circle size="mini" @click="removeConditions(index)"></el-button><span>且(AND)</span>
				</el-col>
				<el-col :span="20" :offset="4">
					<Conditions :conditions="conditionsGroupitem.conditions"/>
				</el-col>
			</el-row>
			<div class="line-text-content"><span class="line-text">或(or)</span></div>
		</div>
		<el-button type="text" @click="addConditions">+触发条件</el-button>
	</div>
		
</template>

<script>
	import Conditions from './Conditions.vue'

	export default {
		name: 'ConditionsGroup',
		data(){
			return {
				initConditionsGroup: this.conditionsGroup,
				nextId: this.conditionsGroup.length + 1
			}
		},
		props: {
			conditionsGroup: {
				type: Array,
				default: () => [{
					id: 1,
					conditions: [{
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
				}]
			},
			fieldList: {
				type: Array
			},
			operatorMap: {
				type: Object
			}
		},
		components: {
			Conditions
		},
		methods: {
			addConditions(){
				let pushItem = {
					id: 3,
					conditions: [{
						id: 1,
						conditionItem: [{
							options: [{id:1,value: 'a',label: 'A'},{id:2,value: 'b',label: 'B'},{id:3,value: 'c',label: 'C'}],
							value: ''
						},{
							options: [{id:1,value: 'a',label: 'A'},{id:2,value: 'b',label: 'B'},{id:3,value: 'c',label: 'C'}],
							value: ''
						},{value: ''}]
					}]
				};
				pushItem.id = this.nextId++;
				this.initConditionsGroup.push(pushItem);
			},
			removeConditions(index){
				this.initConditionsGroup.splice(index,1);
			}
		}
	}
</script>

<style>
	.conditionsgroup{
		width: 600px;
		margin: auto;
		font-family: "Helvetica Neue",Helvetica,"PingFang SC","Hiragino Sans GB","Microsoft YaHei","微软雅黑",Arial,sans-serif;
	}
	.center-container{
		position: relative;
		top: 0;
		left: 0;
	}
	.center-content{
		position: absolute;
		top: 50%;
		transform: translate(0,-50%);
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