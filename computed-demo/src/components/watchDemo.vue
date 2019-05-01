<template>
    <div>
        <h1>监听属性</h1>
        姓名：<input type="text" v-model="userName"/>
        <h1>{{userName}}</h1>
        年龄：<input type="text" v-model="age"/>
        <h1>{{age}}</h1>
        <!--打印userName和age的值-->
        <!-- <h1>{{info}}</h1> -->
        <!--使用计算属性-->
        <h1>{{getUserInfo}}</h1>
        <!--监听对象属性-->
        <h1>监听对象属性</h1>
        姓名：<input type="text" v-model="obj.name"/>
        <h1>{{obj.name}}</h1>
        <!--监听对象-->
        <h1>监听对象</h1>
        姓名：<input type="text" v-model="obj.name"/>
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
           info:'',
           // 对象
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
        // 监听userName的变化
        // 有两个参数，newValue表示变化后的值，oldValue表示变化前的值
        userName:function(newValue,oldValue){
            // console.log('修改前的值：'+oldValue);
            // console.log('修改后的值：'+newValue);
            this.info= '我的姓名:'+ this.userName+',年龄:'+this.age;
        },
        // 监听age的变化
        age:function(newValue,oldValue){
            // console.log('修改前的值：'+oldValue);
            // console.log('修改后的值：'+newValue);
            this.info= '我的姓名:'+ this.userName+',年龄:'+this.age;
        },
        // 监听对象中属性的变化
        // 'obj.name':function(newValue,oldValue){
        //     console.log('修改前的值：'+oldValue);
        //     console.log('修改后的值：'+newValue);
        // }
        // 直接监听对象
        obj:{
            // handler表示默认执行的函数
            handler(newValue,oldValue){
                console.log('修改前的值：')
                console.log(oldValue);
                console.log('修改后的值：');
                console.log(newValue);
            },
            // 表示深度监听 
            // true：表示handler函数会执行
            // false：表示handler函数不会执行
            deep:true
        }
    },
    computed:{
        getUserInfo(){
            return '我的姓名:'+ this.userName+',年龄:'+this.age;
        }
    }
}
</script>

