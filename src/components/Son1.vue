<template>
    <div>儿子1：{{value}}
        <button @click="change">点击事件</button>
        <Grandson1 :value="value" @say="say"></Grandson1>
    </div>
</template>
<script>
//单项数据流 父亲给儿子绑定一个事件
import Grandson1 from './Grandson1';
    export default {
        name:'son1',
        components:{
            Grandson1
        },
        methods:{
            say(){
                // console.log('hello')
            },
            change(){
                // this.$emit('update:value',200)
                this.$emit('input',300)
            }
        },
        props:{
            value:{
                type:Number,
                default: 1
            }
        }
    }
</script>