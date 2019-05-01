<template>
    <div>
        <h1>监听属性</h1>
        姓名：<input type="text" v-model="userName"/>
        <h1>{{userName}}</h1>
        年龄：<input type="text" v-model="age"/>
        <h1>{{age}}</h1>
        obj.name：<input type="text" v-model="obj.name"/>
        <h1>{{obj.name}}</h1>
    </div>
</template>

<script>
export default {
    name:'watchDemo',
    data(){
        return{
           userName:"abc",
           age:23,
           obj:{
               name:'123'
           }
        }
    },
    methods:{
        change(){

        }
    },
    watch:{
        // 监听userName
        userName:function(newValue,oldValue){
            console.log('修改前的值：'+oldValue);
            console.log('修改后的值：'+newValue);
        },
        age:function(newValue,oldValue){
            console.log('修改前的值：'+oldValue);
            console.log('修改后的值：'+newValue);
        },
        // 监听对象的属性
        'obj.name':function(newValue,oldValue){
            console.log('修改前的值：'+oldValue);
            console.log('修改后的值：'+newValue);
        }
    }
}
</script>

