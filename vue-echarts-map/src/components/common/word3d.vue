<template>
  <div>
    <div id="dq"></div>
  </div>
</template>

<script>
import echarts from 'echarts';
import 'echarts/map/js/world.js'
import 'echarts-gl'
export default {
  name: 'dq',
  props: {
  },
  data() {
    return {
      echartsObj: '',
      mapChart:{},
      option :{
        globe: {
          globeRadius: 83,
          baseTexture: '',//贴图 球形和平面的吻合
          silent: true,
          // environment: rgba(0,0,0,0), //背景
          heightTexture: require("../../assets/world.jpg"), //地球的整个纹路
          shading: 'realistic',
          light: {
              main: {
                  color: '#fff',
                  intensity: 0,
                  shadow: false,
                  shadowQuality: 'high',
                  alpha: 55,
                  beta: 10
              },
              ambient: {
                  color: '#fff',
                  intensity: 1
              }
          },
          postEffect: {
              enable: false,
              SSAO: {
                  enable: true,
                  radius: 10
              }
          },

          //地球是否自己转动 autoRotate为true时自己转动
          viewControl: {
              autoRotate: true,
              animationDurationUpdate: 2000,
              targetCoord: ''
          }
        },
        series: [
          {
              name: 'lines3D',
              type: 'lines3D',
              coordinateSystem: 'globe',
              effect: {
                  show: true,
                  period: 2,
                  trailWidth: 3,
                  trailLength: 0.5,
                  trailOpacity: 1,
                  trailColor: '#0087f4'
              },
              blendMode: 'lighter',
              lineStyle: {
                  width: 1,
                  color: '#0087f4',
                  opacity: 0
              },
              data: [],
              silent: false,

          }
        ]
      },
      //平面地球 主要是设置地球的样式
      mapOption: {
        backgroundColor: 'rgba(20,104,121,0.71)',//当和立体球形贴图是海洋的颜色
        visualMap: {
          show: false,
          min: 0,
          max: 100000
        },
        series: [
          {
            type: 'map',
            map: 'world',
            left: 0,
            top: 0,
            right: 0,
            bottom: 0,
            environment: 'rgba(0,0,0,0)',
            boundingCoords: [
              [-180, 90],
              [180, -90]
            ],
            itemStyle: {
              normal: {
                borderWidth: 2,
                borderColor: 'rgb(0,232,232)',//地球纹路的颜色
                areaColor: {
                  type: 'linear',
                  x: 0,
                  y: 0,
                  x2: 0,
                  y2: 1,
                  //相邻每个板块 从上到下的颜色变化
                  colorStops: [{
                    offset: 0.2, color: 'rgb(0,48,62)' // 0% 处的颜色
                    }, {
                      offset: 0.8, color: 'rgba(0,179,188,0.8)' // 100% 处的颜色
                    }
                  ],
                  global: false // 缺省为 false
                },
              }
            }
          }
        ]
      },
      
    }
  },
  mounted() {
    this.initMap()
  },
  methods: {
    initMap(){
      let that = this;
      this.mapChart = echarts.init(document.createElement('canvas'));
      //获取容器并对其初始化
      this.myChart = echarts.init(document.getElementById('dq'))
    //   this.myChart = echarts.init(this.$refs.dq)
      //将平面地球和立体球形的纹路重叠
      this.mapChart.setOption(this.mapOption)
      this.option.globe.baseTexture = this.mapChart
      this.myChart.setOption(this.option);
      setTimeout(() => {
        that.hideClick();
      }, 15000);
      this.myChart.getZr().on('click',function(){
      // this.myChart.on('click',function(e){
          that.hideClick();
      });
    },
    hideClick() {
        this.$emit('hideDqMap',false);
    }
  }
}
</script>
<style scoped>
#dq {
    width: 100%;
    height: 100%;
}
</style>

