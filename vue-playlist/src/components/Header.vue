<template>
    <header @click="changeTitle">
        <h1>{{title1}}{{title}}</h1>
    </header>
</template>

<script>
export default {
    name:"app-header",
    props:{
        title:{
            type:String
        }
    },
    data(){
        return{
            title1:"vue.js Demo"
        }
    },
    methods:{
        changeTitle:function(){
            // this.title = "changed"
            this.$emit("titleChanged","子向父组件传值");
        }
    }
    // beforeCreate:function(){
    //     alert("组件实例化之前执行的函数");
    // },
    // created:function(){
    //     alert("组件实例化完毕，但页面还未显示")
    // },
    // beforeMount:function(){
    //     alert("组件挂载前，页面仍未显示，但虚拟dom已经配置")
    // },
    // mounted:function(){
    //     alert("组件挂载后，页面显示")
    // },
    // beforeUpdate:function(){
    //     alert("组件更新前，页面仍未更新，但虚拟dom已经配置")
    // },
    // updated:function(){
    //     alert("组件更新后，页面显示")
    // },
    // beforeDestroy:function(){
    //     alert("组件销毁前")
    // },
    // destroyed:function(){
    //     alert("组件销毁")
    // }
}
</script>

<style scoped>
header{
    background: lightgreen;
    padding:10px;
}
</style>


