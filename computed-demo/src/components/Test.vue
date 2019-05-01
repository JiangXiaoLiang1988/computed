<template>
    <div>
        <div>您购买了{{info.name}}共{{info.count}}份</div>
        <h1>总价：{{info.count*info.price*info.sale+info.freight}}元</h1>
    </div>
</template>

<script>
export default {
    name:'Test',
    data(){
        return{
            info:{
                userId:1,
                price:15,
                name:'套餐A',
                count:3,
                sale:0.8,
                freight:5
            }
        }
    }
}
</script>

