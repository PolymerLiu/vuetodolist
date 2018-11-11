<template>
    <li @click="handleDelete">{{content}}</li>
</template>


<script>
export default {
    props:['content','index'],
    //子组件接收到click事件，派发一个delete事件供父组件监听
    methods:{
        handleDelete(){
            this.$emit('delete',this.index)
        }

    }
}
</script>

<style>

</style>


