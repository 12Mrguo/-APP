<template>
    <div class="ticket">
        <!-- 头部 -->
        <ticket-header></ticket-header>
        <!-- 循环列表 -->
        <div class="ticket-box">
            <div class="ticket-top flex">
                <div class="ticket-img">
                    <img src="https://img1.qunarzz.com/sight/p0/1410/34/f540a04367d06820af4dfeaf0ad40257.water.jpg_600x330_355f8a51.jpg" alt="">
                </div>
                <router-link class="ticket-link" to="/">
                    <h3>故宫(5A)</h3>
                    <p class="ticket-x">☆☆☆☆☆<span>325891条评论</span></p>
                    <p class="ticket-xx">★★★★★</p>
                    <p class="ticket-jg flex">￥20起<span>东城区|11.4CM</span></p>
                    <p class="ticket-tj"><span class="ticket-lb">送礼包</span><span class="ticket-lx">古建筑</span></p>
                </router-link> 
            </div>
            <div class="ticket-am flex">
                【预售上午场】故宫成人票<span>￥40</span>
            </div>
            <div class="ticket-pm flex">
                【预售下午场】故宫成人票<span>￥40</span>
            </div>
        </div>
        <div class="ticket-kb"></div>
    </div>
</template>
<script>
import TicketHeader from './Header'
import axios from 'axios'
    export default{
        name:"Ticket",
        data(){
            return{
                list:[]
            }
        },
        methods:{
            getTicket(){
                let url = "http://localhost:3030/detail/list"
                axios.get(url).then(function(res){
                    console.log(res.data.BJ);
                })
            }
        },
        mounted() {
            this.getTicket()
        },
        components:{
            TicketHeader
        }
    }
</script>
<style lang="stylus" scoped>
    @import '~@/assets/styles/varibles.styl'
    .flex
        display flex
        justify-content space-between

    .ticket
        .ticket-box
            margin 5px 0
            padding 0 20px
            .ticket-top  
                padding-bottom 10px
                border-bottom 1px solid #eee
                .ticket-img
                    width 40%
                    overflow hidden
                img{
                    width 90%
                    height 100px
                }
            .ticket-link   
                width 60%
                display block
                color #000
                position relative
                h3
                    font-size 20px
                    height 35px
                    line-height 30px
                .ticket-x,.ticket-xx
                    line-height 20px
                    font-size 16px
                    padding-bottom 10px
                .ticket-x span 
                    font-size 12px
                    line-height 20px
                    color #333
                .ticket-xx
                    position absolute 
                    color #FF911C
                    top 35px
                .ticket-jg
                    height 25px
                    font-size 16px
                    color #FF911C
                    span 
                        color #333
                        font-size 12px
                .ticket-tj
                    .ticket-lb,.ticket-lx
                        border 1px solid #eee
                        border-radius 5px
                        padding 3px 10px
                        font-size 12px
                        color #0BB2C9
            .ticket-am,.ticket-pm
                padding 12px
                font-size 14px
            .ticket-pm
                border-top 1px solid #eee
        .ticket-kb
            width 100%
            height 16px
            background #eee

</style>