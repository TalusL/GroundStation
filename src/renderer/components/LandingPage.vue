<template>
  <div sty>
    <div id="map" style="width: 100vw;height: 100vh"></div>
<!--    <div id="wrapper" >-->
<!--      <canvas id="canvas"></canvas>-->
<!--    </div>-->
  </div>

</template>

<script>
  import Model from '../util/model'
  export default {
    name: 'landing-page',
    methods: {
    },
    mounted () {
      // this.model = new Model(document.getElementById('wrapper'), document.getElementById('canvas'))
      var map = new AMap.Map('map', {
        //是否监控地图容器尺寸变化
        resizeEnable: true,
        //初始化地图层级
        zoom:15,
        mapStyle: "amap://styles/dark",
      });
    }
  }
</script>

<style>

</style>
