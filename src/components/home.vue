<template>
    <!--    -->
    <div class='content'>
        <div class="card">
            <div class="cardTop">
                <div class="cardTop-xing">
                    <div class="wangguan"></div>
                </div>
                <span class="cardTop-text">排行榜</span>
            </div>
            <div class="card-content">
                <div class="nav-bar">
                    <div class="btn" v-for="(item,index) in btns" @click="clickBtn(item.name,index)" :class="btnsV===item.name?'btn1':''">家族输水</div>
                </div>
                <ul class="card-list">
                    <li class="card-li" v-for="(item,index) in getAll">
                        <div class="card-li-c">
                            <span class="id">{{item.id}}</span>
                            <img :src="require('../../static/img/tx'+item.img+'.png')" width="35px" height="35px" alt="">
                            <span>{{item.name}}</span>
                        </div>
                        <div class="card-li-c">{{item.value}}</div>
                    </li>
                </ul>
            </div>
        </div>
        <div class="off"></div>

        <div class="xing1"></div>
        <div class="xing2"></div>
        <div class="xing3"></div>
        <div class="xing4"></div>

        <div class="bottomBar">
            <div>这是底色</div>
            <div @click="isshow=!isshow">点这里弹出弹窗</div>
        </div>
        <div class="tips" v-if="isshow">你好世界</div>
    </div>
</template>

<script>
    export default {
        name:'home',
        data(){
            return{
                getAll:[],
                isshow:false,
                
                getdata1:[
                        {"id":1,"img":'1',"name":'小兔子',"value":123344444},
                        {"id":2,"img":'2',"name":'小兔子1',"value":123344444},
                        {"id":3,"img":'1',"name":'小兔子2',"value":123344444},
                        {"id":4,"img":'2',"name":'小兔子3',"value":123344444},
                        {"id":5,"img":'1',"name":'小兔子4',"value":123344444},
                        {"id":6,"img":'2',"name":'小兔子5',"value":123344444},
                        {"id":7,"img":'1',"name":'小兔子6',"value":123344444},
                        {"id":8,"img":'2',"name":'小兔子7',"value":123344444},
                        {"id":9,"img":'1',"name":'小兔子8',"value":123344444},
                        {"id":10,"img":'2',"name":'小兔子9',"value":123344444},
                        {"id":11,"img":'1',"name":'小兔子10',"value":123344444},
                        {"id":12,"img":'2',"name":'小兔子11',"value":123344444},
                        {"id":13,"img":'1',"name":'小兔子12',"value":123344444},
                ],
                getdata2:[
                        {"id":1,"img":'1',"name":'小兔子',"value":123344444},
                        {"id":2,"img":'2',"name":'小甜甜2',"value":123344444},
                        {"id":3,"img":'1',"name":'小甜甜',"value":123344444},
                        {"id":4,"img":'2',"name":'小甜甜',"value":123344444},
                        {"id":5,"img":'1',"name":'小甜甜',"value":123344444},
                        {"id":6,"img":'2',"name":'小甜甜',"value":123344444},
                        {"id":7,"img":'1',"name":'小甜甜',"value":123344444},
                        {"id":8,"img":'2',"name":'小甜甜',"value":123344444},
                        {"id":9,"img":'1',"name":'小甜甜',"value":123344444},
                        {"id":10,"img":'2',"name":'小甜甜',"value":123344444},
                        {"id":11,"img":'1',"name":'小甜甜',"value":123344444},
                        {"id":12,"img":'2',"name":'小甜甜',"value":123344444},
                        {"id":13,"img":'1',"name":'小甜甜',"value":123344444},
                ],
                getdata3:[
                    {"id":1,"img":'1',"name":'小呆呆',"value":123344444},
                    {"id":2,"img":'2',"name":'小呆呆',"value":123344444},
                    {"id":3,"img":'1',"name":'小呆呆',"value":123344444},
                    {"id":4,"img":'2',"name":'小呆呆',"value":123344444},
                    {"id":5,"img":'1',"name":'小呆呆',"value":123344444},
                    {"id":6,"img":'2',"name":'小呆呆',"value":123344444},
                    {"id":7,"img":'1',"name":'小呆呆',"value":123344444},
                    {"id":8,"img":'2',"name":'小呆呆',"value":123344444},
                    {"id":9,"img":'1',"name":'小呆呆',"value":123344444},
                    {"id":10,"img":'2',"name":'小呆呆',"value":123344444},
                    {"id":11,"img":'1',"name":'小呆呆',"value":123344444},
                    {"id":12,"img":'2',"name":'小呆呆',"value":123344444},
                    {"id":13,"img":'1',"name":'小呆呆',"value":123344444},
                ],
                btns:[
                    {name:'家族输水'},
                    {name:'氧气值'},
                    {name:'资源'}
                ],
                btnsV:'家族输水'
            }
        },
        methods:{
            clickBtn(val,i){
                this.btnsV = val;
                if(i===0){
                    this.getAll = this.getdata1
                }else if(i===1){
                    this.getAll = this.getdata2
                }else{
                    this.getAll = this.getdata3
                }
                
            }
        },
        mounted(){
            this.getAll = this.getdata1
        }
    }
</script>

<style scoped>
.content{
    width: 100vw;
    height: 100vh;
    background-color: rgba(41, 53, 17, 1);
    
}
.card{
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
}
.card-content{
    width: 80%;
    height: 70%;
    background: white url(../../static/img/bj1.png) no-repeat center top;
    background-size: 100%;
    padding-top: 70px;
    box-sizing: border-box;
    display: flex;
    flex-wrap: wrap;
    align-items: flex-start;
    justify-content: center;
}
.cardTop{
    width: 65%;
    height: 70px;
    background: url(../../static/img/bj2.png) no-repeat center center;
    background-size: 100% 100%;
    position: absolute;
    top: 13%;
    display: flex;
    justify-content: center;

}
.cardTop-text{
    line-height: 50px;
    color: white;
    font-weight: bold;
}
.cardTop-xing{
    width: 60px;
    height: 60px;
    position: absolute;
    background: url(../../static/img/bj3.png) no-repeat center center;
    background-size: 100% 100%;
    position: absolute;
    top: -80%;
    display: flex;
    justify-content: center;
    align-items: center;
}
.wangguan{
    width: 35px;
    height: 35px;
    background: url(../../static/img/bj4.png) no-repeat center center;
    background-size: 100% 100%;
}

/* 导航按钮 */
.nav-bar{
    width: 100%;
    display: flex;
    justify-content: space-around;
    align-items: flex-start;
}
.btn{
    line-height: 30px;
    background-color: rgb(200, 200, 200);
    color: white;
    font-size: 14px;
    font-weight: 500;
    border-radius: 10px;
    padding: 0 20px;
}
.btn1{
    background-color: yellowgreen;
}
/* 列表内容 */
.card-list{
    width: 90%;
    /* background: red; */
    list-style: none;
    padding: 0;
    margin: 0;
    height: calc(100% - 30px);
    overflow: auto;
}
.card-li{
    height: 45px;
    /* background-color: rebeccapurple; */
    display: flex;
    justify-content: space-between;
    align-content: center;

}
.card-list::-webkit-scrollbar{
                display: none;
}
.card-li-c{
    height: 100%;
    display: flex;
    align-items: center;
}
.card-li-c>img{
    margin-right: 5px;
}



.id{
    background-color: rgb(250, 169, 35);
    width: 20px;
    line-height: 20px;
    color: white;
    border-radius: 50%;
    display: inline-block;
    text-align: center;
    margin: 0 5px;
}



.off{
    width: 40px;
    height: 40px;
    background: url(../../static/img/bj5.png) no-repeat center center;
    background-size: 100% 100%;
    position: absolute;
    bottom: 7%;
    left: 50%;
    transform: translateX(-50%);
}

.bottomBar{
    width: 100%;
    height: 35px;
    position: fixed;
    bottom: 0;
    left: 0;
    background-color: yellowgreen;
    display: flex;
    justify-content: space-around;
    align-items: center;
}
.tips{
    width: 60%;
    height: 200px;
    background: chocolate;
    color: white;
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    text-align: center;
    z-index: 10;
}
.xing1{
    width: 40px;
    height: 40px;
    position: absolute;
    left: 5%;
    top: 10%;
    background: url(../../static/img/xing1.png) no-repeat center center;
    background-size: 100%;
}
.xing2{
    width: 20px;
    height: 20px;
    position: absolute;
    left: 2%;
    top: 50%;
    background: url(../../static/img/xing2.png) no-repeat center center;
    background-size: 100%;
}
.xing3{
    width: 20px;
    height: 20px;
    position: absolute;
    bottom: 70%;
    right: 2%;
    background: url(../../static/img/xing3.png) no-repeat center center;
    background-size: 100%;
}
.xing4{
    width: 45px;
    height: 45px;
    position: absolute;
    bottom: 8%;
    right: 2%;
    background: url(../../static/img/xing4.png) no-repeat center center;
    background-size: 100%;
}
    
   
</style>