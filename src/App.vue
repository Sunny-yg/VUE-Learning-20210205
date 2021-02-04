<template>
    <div>
        <h2>人员登记系统</h2>
        <div class="people_list">
            <ul>
                <li>姓 名：<input type="text" v-model="userInfo.username"></li>

                <li>年 龄：<input type="text" v-model="userInfo.age"/></li>

                <li>性 别：
                    <input type="radio" name="sex" id="sex1" value="1" v-model="userInfo.sex"><label for="sex1">男</label>

                    <input type="radio" name="sex" id="sex2" value="2" v-model="userInfo.sex"><label for="sex2">女</label>
                </li>
                
                <li>城 市:
                    <select v-model="userInfo.city">
                        <option v-for="(item,index) in userInfo.cityList" :key="index" :value="item">{{item}}</option>
                    </select>

                </li>    

                <li>爱 好：
                    <span v-for="(item,index) in userInfo.hobby" :key="index">
                       <input type="checkbox" :id="'ch'+index" v-model="item.checked">
                       <label for="'ch'+index">{{item.title}}</label>

                    </span>

                </li>

                <li>备 注:
                    <textarea cols="30" rows="10" v-model="userInfo.mark"></textarea>
                
                
                </li>     

            </ul>
            <button @click="doSubmit()" class="submit">获取表单的内容</button>

            <br><br>
            <pre>
                {{userInfo}}
            </pre>
        </div>       

    </div>
</template>

<script>
    export default {
        data(){
            return{
                userInfo:{
                   username:"zhangsan",
                   age:"",
                   sex:"1",
                   cityList:["北京","上海","深圳"],
                   city:"上海",
                   hobby:[{
                       title:"吃饭",
                       checked:true
                   },
                   {
                       title:"睡觉",
                       checked:true
                   },
                   {
                       title:"敲代码",
                       checked:false
                   }
                   ],
                   mark:""
                }             
                
            };
        },
        methods:{
           
            doSubmit(){
                console.log(this.userInfo);
                
            },

        }
       
    }
</script>

<style>
ul{
    list-style-type: none;
}

h2{
    text-align: center;
}
</style>