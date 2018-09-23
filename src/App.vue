<template>
    <div id="app">
        <ConditionsGroup/>
    </div>
</template>

<script>
    import ConditionsGroup from './components/ConditionsGroup.vue'

    let fieldList = [{
        value: 'text1',
        label: '陈列上报编号',
        type: 'text'
    },{
        value: 'text2',
        label: '负责人',
        type: 'text'
    },{
        value: 'text3',
        label: '负责人所在部门',
        type: 'text'
    },{
        value: 'text4',
        label: '产品',
        type: 'text'
    },{
        value: 'num1',
        label: '排面数',
        type: 'number'
    },{
        value: 'num2',
        label: '割箱数',
        type: 'number'
    },{
        value: 'num3',
        label: '整箱数',
        type: 'number'
    },{
        value: 'num4',
        label: '堆头数',
        type: 'number'
    }]
    let operatorMap = {
        text: [{
            value: 'include',
            label: '包含'
        },{
            value: 'notInclude',
            label: '不包含'
        },{
            value: 'equal',
            label: '等于'
        },{
            value: 'notEqual',
            label: '不等于'
        },{
            value: 'empty',
            label: '为空（未填写）'
        },{
            value: 'notEmpty',
            label: '不为空'
        }],
        number: [{
            value: 'equal',
            label: '等于'
        },{
            value: 'gt',
            label: '大于'
        },{
            value: 'lt',
            label: '小于'
        }]
    }
    window.initConditionsGroup = [{
        id: 1,
        condition: [{
            id: 1,
            fieldValue: 'text1',
            mapValue: 'equal',
            value: '110'
        },{
            id: 2,
            fieldValue: 'text3',
            mapValue: 'equal',
            value: '技术部'
        },{
            id: 3,
            fieldValue: 'num4',
            mapValue: 'gt',
            value: '100'
        }]
    },{
        id: 2,
        condition: [{
            id: 1,
            fieldValue: 'text1',
            mapValue: 'equal',
            value: '110'
        },{
            id: 2,
            fieldValue: 'text3',
            mapValue: 'equal',
            value: '技术部'
        },{
            id: 3,
            fieldValue: 'num4',
            mapValue: 'gt',
            value: '100'
        }]
    }];

    export default {
        name: 'app',
        data: () => ({
          fieldList: fieldList,
          operatorMap: operatorMap,
          initConditionsGroup: window.initConditionsGroup
        }),
        components: {
          ConditionsGroup, 
        }
    }
</script>

<style>

</style>
