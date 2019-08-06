<template>
  <div class="mainCont">
    <div id="map"></div>
    <div class="rightView">
      <div class="title">飞行姿态</div>
      <div id="wrapper" >
        <canvas id="canvas"></canvas>
      </div>
    </div>

  </div>

</template>

<script>
  import Model from '../util/model'
  export default {
    name: 'landing-page',
    data(){
      return {
        model:{}
      }
    },
    methods: {
      /**
       * 加载地图
       */
      createMap(){
        if (window.AMap){
          var map = new window.AMap.Map('map', {
            // 是否监控地图容器尺寸变化
            resizeEnable: true,
            // 初始化地图层级
            zoom: 15,
            mapStyle: 'amap://styles/dark'
          });
        }
      },
      /**
       * 加载飞行器模型
       */
      loadModel(){
        this.model = new Model(document.getElementById('wrapper'), document.getElementById('canvas'));
      }
    },
    mounted () {
      this.loadModel();
      this.createMap();
    },
    created() {
      window.addEventListener('resize',()=>{
        this.$nextTick(()=>this.model.resize());
      });
    }
  }
</script>

<style scoped lang="less">
  .mainCont{
    #map{
      width: 100vw;
      height: 100vh;
    }
    .rightView{
      position: absolute;
      right: 2vw;
      top: 2vw;
      background-color: rgba(0,0,0,0.6);
      border-radius: 1vw;
      .title{
        color: #ffffff;
        font-size: 2vw;
        line-height: 3vw;
        text-align:center;
      }
      #wrapper{
        width: 18vw;
        #canvas{
          width: 180px;
          height: 180px;
        }
      }
    }

  }
</style>
