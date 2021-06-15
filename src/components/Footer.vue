<template>
    <footer>
        <div class="foot-container">
            <div class="foot-left"><!-- v-for="(item,index) in footList" :key="index" -->
                <!-- <h2>{{ item.title }}</h2>
                <ul>
                    <li v-for="(sub_item,index) in item.subList" :key="index">
                        <router-link :to="sub_item.link">{{ sub_item.sub_title }}</router-link>
                    </li>
                </ul> -->
                <Map></Map>
            </div>
            <div class="foot-middle">
                <h2>联系我们</h2>
                <ul>
                    <li style="color: #FF8724;">
                        <span style="float:left;margin-right: 8px;"><i class="el-icon-location-outline"></i></span>
                        <div style="display: inline-block;">
                            重庆市江北区盘溪路420号<br>龙湖源著北区3栋44-11
                        </div>
                    </li>
                    <li style="color: #67C23A;"><i class="el-icon-phone"></i>服务热线：023-68851944</li>
                    <li style="color: #67C23A;"><i class="el-icon-printer"></i>网址：<a href="www.cqjhn.com.cn" style="color: #67C23A;text-decoration:none;">www.cqjhn.com.cn</a></li>
                    <li style="color: #FF8724;">
                        <span style="float:left;margin-right: 8px;"><i class="el-icon-location-outline"></i></span>
                        <div style="display: inline-block;">
                            生产地址：重庆市北碚区金龙工业园区<br>（双元大道北侧）
                        </div>
                    </li>
                </ul>
            </div>
            <div class="foot-right">
                <h4>扫描二维码关注我们</h4>
                <img src="http://image.fast.126net.cn/group1/M00/04/53/wKgADFuq_KGASIxqAAAIG8_FUak359.png" alt="">
                <!-- <h5><router-link to="">View More >></router-link></h5> -->
            </div>
        </div>
        <div class="foot-bottom">
            <div>© Copyrights 2020 重庆锦翰南环保工程有限公司. All rights reserved </div>
            <div>渝ICP备19000065号</div>
        </div>
    </footer>
</template>

<script>
import Map from './Map'
export default {
  name: "Footer",
  components:{
      Map
  },
  data() {
    return {
        footList: [
            {
                title: '产品体系',
                subList:[
                    {
                        sub_title: '智能产品',
                        link: ''
                    },
                    {
                        sub_title: '能效',
                        link: ''
                    },
                    {
                        sub_title: '新能源',
                        link: ''
                    }
                ]
            },
            {
                title: '解决方案',
                subList:[
                    {
                        sub_title: '基于用户蓄电池分布式储能服务平台',
                        link: ''
                    },
                    {
                        sub_title: '城市能源管控服务云平台',
                        link: ''
                    },
                    {
                        sub_title: '需求侧能源管控平台',
                        link: ''
                    },
                    {
                        sub_title: '智慧水务管控一体化平台',
                        link: ''
                    }
                ]
            },
            {
                title: '关于我们',
                subList: [
                    {
                        sub_title: '了解我们',
                        link: ''
                    },
                    {
                        sub_title: '发展历程',
                        link: ''
                    },
                    {
                        sub_title: '奖项荣誉',
                        link: ''
                    },
                    {
                        sub_title: '新闻动态',
                        link: ''
                    }
                ]
            }
        ],
        viewList: [
            {
                path: 'flickr01.jpg',
                link: ''
            },
            {
                path: 'flickr02.jpg',
                link: ''
            },
            {
                path: 'flickr03.jpg',
                link: ''
            },
            {
                path: 'flickr04.jpg',
                link: ''
            },
            {
                path: 'flickr05.jpg',
                link: ''
            },
            {
                path: 'flickr06.jpg',
                link: ''
            },
            {
                path: 'flickr07.jpg',
                link: ''
            },
            {
                path: 'flickr08.jpg',
                link: ''
            }
        ]
    }
  }
};
</script>

<style lang="scss" scoped>
    footer {
        width: 100%;
        padding-top: 2%;
        .foot-container {
            z-index: 1;
            background: #009262;
            width: 100%;
            padding: 3% 0 3% 3%;
            box-sizing: border-box;
            display: flex;
            h2 {
                color: #fff;
                margin: 0 0 20px 0;
                font-size: 16px;
                font-family: "Open Sans", sans-serif;
                font-weight: 600;
                text-transform: uppercase;
                letter-spacing: 1px;
            }
            ul {
                li {
                    padding: 5px;
                    padding-left: 0;
                    padding-right: 0;
                    color: #969595;
                    font-size: 14px;
                }
            }
            .foot-left {
                // margin-right: 5%;
                ul {
                    li {
                        padding: 10px;
                        // border-bottom: 1px solid #ffffff;
                        a {
                            display: block;
                            color: #ffffff;
                            font-size: 14px;
                            text-decoration: none;
                            transition: all .3s;
                            &:hover {
                                color:#FF8724;
                                transform: scale(1.2);
                            }
                        }
                    }
                }
            }
            .foot-middle {
                margin-left: 5%;
                position: relative;
                text-align: left;
                
                &::before {
                    position: absolute;
                    content: '';
                    height: 80%;
                    width: 1px;
                    background-color: #ffffff;
                    left: -30px;
                    top: 10%;
                }
                ul>li>i{
                    margin-right: 8px;
                }
            }
            .foot-right {
                text-align: center;
                color: #ffffff;
                margin-left: 10%;
                img {
                    width: 150px;
                    height: 150px;
                    padding-top: 20px;
                }
                ul {
                    display: grid;
                    grid-template-columns: repeat(4, 25%);
                    grid-template-rows: repeat(2, 42%);
                    gap: 3px;
                    li:hover {
                        animation: pulse .5s linear;
                    }
                }
                h5 {
                    text-align: right;
                    a {
                    color: #5FB878;
                        text-decoration: none;
                    }
                }
            }
        }
        .foot-bottom {
            background: #009262;
            padding: 15px 0;
            box-sizing: border-box;
            width: 100%;
            color: #ffffff;
            font-size: 14px;
            display: flex;
            justify-content: space-around;
        }
    }

</style>
