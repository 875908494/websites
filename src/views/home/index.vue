<template>
    <div>
        <el-carousel trigger="click" height="500px" @change="loadAnimate">
            <el-carousel-item v-for="(item,index) in sliderList" :key="index">
                <figure>
                    <img :src="'../../static/img/slider/'+item.img" width="100%"/>
                    <figcaption>
                        <h1 :class="{ bounceInDown:slider_index==index }">{{ item.title }}</h1><br>
                        <p :class="{ fadeInUp:slider_index==index }">{{ item.abstract }}</p><br>
                        <p :class="{ fadeInUp:slider_index==index }">{{ '电话：' +  item.tel }}</p><br>
                        <p :class="{ fadeInUp:slider_index==index }">{{ '地址：' +  item.address }}</p><br>
                        <router-link :to="item.link">
                            <el-button class="slider-button" round :class="{ fadeInUp:slider_index==index }">了解详情 >></el-button>
                        </router-link>
                    </figcaption>
                </figure>
            </el-carousel-item>
        </el-carousel>
        <div class="home-service">
            <h4>公司<span style="color:#009262">介绍</span></h4>
            <p style="color:#009262">COMPANY PROFILE</p>
            <div class="company-desc">
                <img src="http://image.fast.126net.cn/group1/M00/04/53/wKgADFuq7MyAPl1aAAaDj7Q4TgM114.png" alt="介绍" style="width:40vw;height:60vh;">
                <p v-html="desc">
                </p>
            </div>
            <div href="#" class="more"></div>
        </div>
        <div class="home-friends">
            <div class="friends-container">
                <h4>服务介绍</h4>
                <p>SERVICE INTRODUCTION</p>
                <ul>
                    <!-- <transition-group enter-active-class="animated zoomInLeft" leave-active-class="animated zoomOutRight"> -->
                        <li v-for="item in 4" :key="item">
                            <img :src="`../../../static/img/friends/friends${item}.png`">
                            <span>绿色建材</span>
                        </li>
                    <!-- </transition-group> -->
                </ul>
            </div>
        </div>
        <div class="case-display">
            <h4>案列<span style="color:#009262">展示</span></h4>
            <p style="color:#009262">CASE SHOW</p>
            <ul>
                
                <li v-for="(item,index) in services" :key="index">
                    <div class="service-box">
                        <img :src="`../../../static/img/services/case${index+1}.jpg`">
                        <div class="service-info"><p>{{ item.info }}</p></div>
                    </div>
                    <p style="line-height:50px">{{ item.title }}</p>
                </li>
                
            </ul>
        </div>
        <div class="home-news">
            <div class="news-container">
                <h4>新闻资讯</h4>
                <p>NEWS INFORMATION</p>
                <ul>
                    <li v-for="item in 4" :key="item">
                        <img :src="`../../../static/img/news/news${item}.jpg`">
                        <span class="news-title">国开行棚改贷款累计发放突破万亿</span>
                        <span class="news-content">新华社北京5月12日电（记者 姜琳、陶俊洁）记者12日从国家开发银行了</span>
                    </li>

                </ul>
            </div>
        </div>
    </div>
</template>
<script>
import { home } from '../../http/home';

export default {
    name: "Home",
    data(){
        return {
            slider_index: 0,
            sliderList: [
                {
                    title: '加盟锦翰南环保，开启财富之门',
                    abstract: '诚邀您的加盟',
                    tel: '18983416555',
                    address: '重庆市九龙坡区石坪桥正街116号3-25-3',
                    img: 'home1.jpg',
                    link: ''
                },
                {
                    title: '环保彩色透水路面',
                    abstract: '材料研发、专项施工、技术服务的高新技术企业',
                    tel: '18983416555',
                    address: '重庆市九龙坡区石坪桥正街116号3-25-3',
                    img: 'home2.jpg',
                    link: ''
                }
            ],
            kind:[
                {
                    title: '构建能源服务生态图',
                    info: '让天下企业用“好”能源'
                },
                {
                    title: '智慧能管平台',
                    info: '基于物联网、大数据、区块链等先进技术'
                },
                {
                    title: '能效产品',
                    info: '汇聚行业先进能效产品与技术'
                },
                {
                    title: '根据地式能源服务大厅',
                    info: '为您提供多种多样的综合服务'
                }
            ],
            services:[
                {
                    title: '晶聚合03',
                    info: '“纵向到企业、横向跨行业、覆盖全工业”，实现供给侧与需求侧双向互动。'
                },
                {
                    title: '龙陵黄龙玉石',
                    info: '提供平台、智能终端、能效产品与新技术，实现“能源互联网+售电+能源服务”的综合能源服务。'
                },
                {
                    title: '卡布基洛.咖啡玉石',
                    info: '提供能源管理系统装备、技术、人才的整体服务解决方案，降低生产成本，提高竞争力。'
                },
                {
                    title: '晶聚合01',
                    info: '“纵向到企业、横向跨行业、覆盖全工业”，实现供给侧与需求侧双向互动。'
                },
                {
                    title: '晶聚合02',
                    info: '提供平台、智能终端、能效产品与新技术，实现“能源互联网+售电+能源服务”的综合能源服务。'
                },
                {
                    title: '晶聚合砂石',
                    info: '提供能源管理系统装备、技术、人才的整体服务解决方案，降低生产成本，提高竞争力。'
                }
            ],
            desc:'&emsp;&emsp;重庆锦翰南环保工程有限公司成立于2011年，注册资金500万，是一家专业从事环保彩色透水路面材料研发、专项施工、技术服务的高新技术企业。</br></br>&emsp;&emsp;环保彩色透水路面技术在上个世纪90年代由欧洲传入中国，其独特的蜂巢多孔式的产品结构特点，对城市内涝改善、PM2.5固体颗粒物吸附、城市温度湿度调节、有限水资源保护等等方面，有着积极有效的正面作用。中国住房和城乡建设部2014年10月发布的《海绵城市建设技术指南》，将多孔透水混凝土技术列为海绵城市建设推荐产品。</br></br>&emsp;&emsp;目标清晰、谋定后动，打造积极进取，科学高效的管理团队，为客户提供专业、成功的管理服务，为区域合作伙伴提供全面、一站式的工程服务。重庆锦翰南环保工程有限公司，与您携手共创辉煌！'
        }
    },
    created(){
        this.$emit('headFix', ['fixed',false]);
        // home()
        // .then(data=>{
        //     console.log(data)
        // })
        // .catch(err => {
        //     this.$message.error(err.message);
        // });
    },
    methods:{
        loadAnimate(index){
            this.slider_index = index;
        }
    }
}
</script>
<style lang="scss" scoped>
    @mixin self_icon {
        &::before {
            border-left: 50px solid #DADADA;
            border-right: 50px solid #DADADA;
            bottom: 0;
            content: "";
            height: 1px;
            margin-left: -70px;
            position: absolute;
        }
        &::after {
            background: #FF8724 none repeat scroll 0 0 padding-box content-box;
            border-bottom: 1px solid #DADADA;
            border-left: 1px solid #DADADA;
            bottom: -10px;
            content: "";
            left: 50%;
            margin-left: -16px;
            padding: 0 0 8px 8px;
            position: absolute;
            transform: rotate(-45deg);
        }
    }
    figure {
        color: #ffffff;
        text-align: left;
        &::before {
            background: rgba(0, 0, 0, 0.4) none repeat scroll 0 0;
            content: "";
            height: 100%;
            position: absolute;
            width: 100%;
        }
        figcaption {
            bottom: 0;
            left: 6%;
            margin: 0 auto;
            position: absolute;
            right: 6%;
            top: 20%;
            width: 1170px;
            padding: 0 15px;
            h1 {
                font-size: 46px;
            }
            p {
                font-size: 18px;
                font-weight: 400;
            }
            .slider-button {
                background-color: #FE8724;
                border-color: #FE8724;
                color: #ffffff;
                width: 180px;
                height: 40px;
                font-size: 18px;
                transition: transform 2s;
                &:hover {
                    transform: translateY(10px);
                }
            }
        }
    }
    .home-kind {
        box-sizing: border-box;
        background-color: #EBEEF5;
        padding: 0 5%;
        display: flex;
        li {
            padding: 1%;
            text-align: left;
            position: relative;
            box-sizing: border-box;
            width: 25%;
            h3{
                display: inline-block;
                div {
                    margin-top: 1%;
                    height: 2px;
                    width: 40px;
                    background-color: #0984E3;
                }
            }
            p {
                margin-top: 1.5%;
                font-size: 14px;
                color: gray;
            }
            h3>div {
                transition: width .5s;
            }
            &:hover {
                background-color: #ffffff;
                transition: background-color .5s;
                h3>div{
                    width: 100%;
                }
            }
            &:not(:first-child)::before {
                content: '';
                position: absolute;
                width: 1px;
                height: 80%;
                left: 0;
                background-color: #D6D6D6;
            }
            
        }
    }
    .home-service {
        margin-top: 3%;
        &>p {
            margin-top: 1%;
            font-size: 14px;
            color: gray;
            position: relative;
            @include self_icon;
            &::before {
                left: 49.9%;
                top: 174%;
                width: 43px;
            }
            &::after {
                height: 22px;
                left: 50%;
                top: 140%;
                width: 22px;
            }
        }
        ul {
            margin-top: 5%;
            padding: 0 10%;
            display: grid;
            width: 100%;
            grid-template-columns: repeat(3,33.33333%);
            li {
                .service-box {
                    margin-left: 50%;
                    transform: translateX(-50%);
                    display: flex;
                    overflow: hidden;
                    width: 100%;
                    padding: 0 10px 20px;
                    box-sizing: border-box;
                    // border-radius: 50%;
                    img, .service-info {
                        transition: all 0.4s ease-in-out 0s;
                    }
                    &:hover {
                        img, .service-info {
                            transform: translateX(-80%);
                        }
                    }
                    img {
                        width: 100%;
                        height: auto;
                    }
                    .service-info {
                        width: 80%;
                        height: 100%;
                        background: #f1f1f1;
                        padding: 20% 25% 0 5%;
                        position: absolute;
                        top: 0;
                        right: -110%;
                        p {
                            font-weight: 600;
                        }
                    }
                }
            }
        }
    }
    .home-friends {
        margin-top: 5%;
        height: 50vh;
        padding: 20px 0;
        background: url(http://image.fast.126net.cn/group2/M00/01/8F/wKgADluq75yAVf-0AAFVciCOcYM640.jpg);
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
        position: relative;
        .friends-container {
            padding-right: 15px;
            padding-left: 15px;
            position: relative;
            h4 {
                color: #ffffff;
            }
            &>p {
                font-size: 14px;
                margin-top: 1%;
                color: #ffffff;
                @include self_icon;
                &::before {
                    left: 50%;
                    top: 144%;
                    width: 29.5px;
                }
                &::after {
                    height: 12px;
                    left: 50%;
                    top: 130.5%;
                    width: 12px;
                }
            }
            ul {
                display: flex;
                width: 95%;
                margin-top: 5%;
                position: absolute;
                cursor: pointer;
                margin-left: 50%;
                transform: translateX(-50%);
                li {
                    width: 300%;
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    flex-direction: column;
                    span{
                        color:#ffffff;
                    }
                }
            }
        }
    }
    .home-news {
        margin-top: 1%;
        height: 500px;
        padding: 20px 0;
        width: 100%;
        background: url(http://image.fast.126net.cn/group1/M00/04/53/wKgADFuq9WSAWrILAAEkbCJCN7o440.jpg);
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
        position: relative;
        .news-container {
            padding-right: 15px;
            padding-left: 15px;
            position: relative;
            height: 100%;
            h4 {
                color: #ffffff;
            }
            &>p {
                font-size: 14px;
                margin-top: 1%;
                color: #ffffff;
                @include self_icon;
                &::before {
                    left: 50%;
                    top: 144%;
                    width: 29.5px;
                }
                &::after {
                    height: 12px;
                    left: 50%;
                    top: 130.5%;
                    width: 12px;
                }
            }
            ul {
                display: flex;
                width: 70%;
                height: 70%;
                margin-top: 4%;
                background-color: #ffffff;
                position: relative;
                
                margin-left: 50%;
                transform: translateX(-50%);
                li {
                    width: 20%;
                    margin-top: -2vh;
                    display: flex;
                    margin-left: 4%;
                    justify-content: center;
                    align-items: center;
                    flex-direction: column;
                    img{
                        width: 15vw;
                        height: 10vw;
                        cursor: pointer;
                        transition: all .5s;
                        &:hover {
                            width: 16vw;
                            height: 11vw;
                            // line-height: 15vh;
                            // font-size: 18px;
                            
                        }
                        
                    }
                    .news-title{
                        line-height: 2;
                        width: 13vw;
                        color: #333333;
                        font-weight: 700;
                        white-space: nowrap;
                        text-overflow: ellipsis;
                        overflow: hidden;
                        word-break: break-all;
                    }
                    .news-content{
                        color: #999999;
                        font-size: 14px;
                        text-align: left;
                        overflow: hidden;
                        line-height: 150%;
                    }
                }
            }
        }
    }
    .case-display{
        margin-top: 3%;
        padding: 0 5%;
        &>p {
            margin-top: 1%;
            font-size: 14px;
            color: gray;
            position: relative;
            @include self_icon;
            &::before {
                left: 49.9%;
                top: 174%;
                width: 43px;
            }
            &::after {
                height: 22px;
                left: 50%;
                top: 140%;
                width: 22px;
            }
        }
        ul {
            margin-top: 5%;
            display: grid;
            width: 100%;
            grid-template-columns: repeat(3,33.33333%);
            li {
                min-width: 380px;
                min-height: 380px;
                .service-box {
                    margin-left: 50%;
                    transform: translateX(-50%);
                    display: flex;
                    overflow: hidden;
                    min-width: 380px;
                    min-height: 380px;
                    padding: 0 10px 10px 10px;
                    box-sizing: border-box;
                    // border-radius: 50%;
                    img, .service-info {
                        transition: all 0.4s ease-in-out 0s;
                    }
                    &:hover {
                        img, .service-info {
                            transform: translateX(-91%);
                        }
                    }
                    img {
                        width: 100%;
                        height: auto;
                    }
                    .service-info {
                        width: 80%;
                        height: 100%;
                        color: #ffffff;
                        background: #009262;
                        padding: 20% 25% 0 5%;
                        position: absolute;
                        top: 0;
                        right: -110%;
                        p {
                            font-weight: 600;
                        }
                    }
                }
            }
        }
    }
// 动画类
.bounceInDown {
    animation: bounceInDown 1s linear;
}
.fadeInUp {
    animation: fadeInUp 1s linear;
}
.company-desc{
    background-color: rgba(1,93,68,1);
    position: relative;
    z-index: 999;
    margin: 5vw 15vw;
    height: 60vh;
    width: 70%;
    img {
        position: absolute;
        z-index: 998;
        left: 0;
    }
    p{
        width: 25vw;
        height: 60vh;
        font-size: 14px;
        font-family: '微软雅黑';
        line-height: 1.5;
        position: absolute;
        overflow: hidden;
        top: 5%;
        right: 2%;
        color: #ffffff;
        text-align: left;
    }
    
}
.more {
        width: 100px;
        height: 100px;
        line-height: 90px;
        position: absolute;
        margin-top: -7%;
        left: 47%;
        z-index: 999999;
        border-color: rgba(0, 0, 0,0);
        color: rgba(0, 0, 0,0);
        background-color: rgba(0, 0, 0,0);
        background-image: url(http://image.fast.126net.cn/group2/M00/01/8F/wKgADluq7iCAVKPsAAAH3G1OOmk270.png);
        background-repeat: no-repeat;
    }
</style>