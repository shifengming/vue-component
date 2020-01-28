<template>
    <div>
        孙子：{{value}}
        <!-- {{this.parent.isSmoke}} -->
        <button @click="changeParent">修改父亲</button>
    </div>
</template>
<script>
export default{
    mounted(){
        // Provide在当前的实例上vm._prviode
        // inject vm.$parent._prvoide
        this.$nextTick(()=>{
            this.$bus.$emit('有人')
        })
    },
    // inject:[
    //     'parent'
    // ],
    methods:{
        changeParent(){
            // eventBus
            //$dispatch 只会通知自己的父亲
            // this.$parent.$emit('input',200);
            this.$dispatch('input',200)
            // window.console.log(this.$dispatch)
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