<template>
    <div>
        <h1>修改计算属性</h1>
        <h2>num:{{num}}</h2>
        <h2>计算属性num2:{{num2}}</h2>
        <button @click="change">改变计算属性的值</button>
    </div>
</template>

<script>
import { get } from 'http';
export default {
    name:'ComputedDemo2',
    data(){
        return{
            num:100
        }
    },
    computed:{
         num2:{
             // 当计算属性要修改时先触发set方法
             // 读取当前计算属性中的值,get方法可以隐藏，默认进入的是get方法
             get:function(){
                return this.num-10;
             },
             set:function(val){
                 this.num=val;
             }
         }
    },
    methods:{
        change(){
            // 计算属性不能直接修改
            this.num2=60;
        }
    }
}
</script>

