<template>
    <div>
        <baidu-map class="map" :center="map.center" :zoom="map.zoom" @ready="handler">
            <!--缩放-->
            <bm-navigation anchor="BMAP_ANCHOR_TOP_LEFT"></bm-navigation>
            <!--定位-->
            <bm-geolocation anchor="BMAP_ANCHOR_BOTTOM_RIGHT" :showAddressBar="true" :autoLocation="true"></bm-geolocation>
            <!--点-->
            <bm-marker :position="map.center" :dragging="map.dragging" animation="BMAP_ANIMATION_DROP">
                <!--提示信息-->
                <bm-info-window :show="map.show">
                    <span style="color:#cc5522;">重庆市江北区盘溪路</span>
                    <a target="_blank" href="https://map.baidu.com/@11867758,3429056,13z" style="margin-left:5px;font-size:12px;color:#3d6dcc;font-weight:normal;text-decoration:none;">详情»</a>
                    <br>
                    <br>
                    <span>地址：龙湖源著北区3栋44-11</span>
                </bm-info-window>
            </bm-marker>
        </baidu-map>
    </div>
</template>
 
<script>
    export default {
        name: "demo",
        data: () => ({
            map:{
                center: {lng: 106.490056, lat: 29.608385},
                zoom: 17,
                show: true,
                dragging: true
            },
        }),
        methods: {
            handler ({BMap, map}) {
                let me = this;
                console.log(BMap, map)
                // 鼠标缩放
                map.enableScrollWheelZoom(true);
                // 点击事件获取经纬度
                map.addEventListener('click', function (e) {
                    console.log(e.point.lng, e.point.lat)
                })
            }
        }
    }
</script>
 
<style scoped>
    .map {
        width: 50vw;
        height: 15vw;
    }
</style>