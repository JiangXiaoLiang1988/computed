<template>
    <div>
        <h1>计算属性</h1>
        <!-- <div>您购买了{{info.name}}共{{info.count}}份</div> -->
        <!-- 使用计算属性：和绑定普通属性一样 -->
        您购买了<input type="text" v-model="info.name" />
        数量<input type="text" v-model="info.count" />
        
        <h1>使用计算属性获取总价：{{totalPrice}}元</h1>
        <button @click="getTotalPrice">计算属性</button>
        <h1>使用方法获取总价：{{data}}元</h1>
    </div>
</template>

<script>
export default {
    name:'ComputedDemo',
    data(){
        return{
            info:{
                userId:1,
                price:15,
                name:'套餐A',
                count:3,
                sale:0.8,
                freight:5
            },
            data:0
        }
    },
    computed:{
        // 定义计算属性totalPrice
        // totalPrice:function(){
        //     return this.info.count*this.info.price*this.info.sale+this.info.freight;
        // }
        // 使用ES6写法
        totalPrice(){
            console.log('计算属性');
            return this.info.count*this.info.price*this.info.sale+this.info.freight;
        }
    },
    methods:{
        getTotalPrice(){
            console.log('方法');
            this.data= this.info.count*this.info.price*this.info.sale+this.info.freight;
        }
    }
}
</script>

