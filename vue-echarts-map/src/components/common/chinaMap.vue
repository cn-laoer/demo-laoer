<template>
  <div>
    <div id="mapChart" class="chart"></div>
  </div>
</template>

<script>
import echarts from 'echarts'
import cityMap from "@/js/china-main-city-map.js";
import 'echarts/map/js/china.js'
import 'echarts/map/js/province/shanxi1.js'
export default {
  name: 'chart',
  components: {
    // vHome
  },
  data() {
    return {
      chart: null,
      xianOption: { // 进行相关配置
        backgroundColor: "rgba(0,0,0,0)",
        tooltip: {}, // 鼠标移到图里面的浮动提示框
        dataRange: {
          show: false,
          min: 0,
          max: 1000,
          text: ['High', 'Low'],
          realtime: true,
          calculable: true,
          color: ['orangered', 'yellow', 'lightskyblue']
        },
        geo: { // 这个是重点配置区
          map: '陕西', // 表示中国地图
          roam: true,
          label: {
            normal: {
              show: true, // 是否显示对应地名
              textStyle: {
                color: 'rgba(255,255,255)'
              }
            }
          },
          itemStyle: {
            normal: {
              borderColor: 'rgba(255, 255, 255, 0.5)',
              areaColor: "rgba(0, 141, 255, 1)",
              // borderColor: "#1dc199",
              borderWidth: 1
            },
            emphasis: {
              areaColor: null,
              shadowOffsetX: 0,
              shadowOffsetY: 0,
              shadowBlur: 20,
              borderWidth: 0,
              shadowColor: 'rgba(0, 0, 0, 0.5)'
            }
          }
        },
        series: [{
            type: 'scatter',
            coordinateSystem: 'geo' // 对应上方配置
          },
          {
            name: '启动次数', // 浮动框的标题
            type: 'map',
            geoIndex: 0,
            data: [
            //   {
            //   "name": "北京",
            //   "value": 599
            // }, {
            //   "name": "上海",
            //   "value": 142
            // }, {
            //   "name": "黑龙江",
            //   "value": 44
            // }, {
            //   "name": "深圳",
            //   "value": 92
            // }, {
            //   "name": "湖北",
            //   "value": 810
            // }, {
            //   "name": "四川",
            //   "value": 453
            // }
              {
                "name": "陕西",
                "value": 900
              }
            ]
          }
        ]
      }
    }
  },
  mounted() {
    this.chinaConfigure();
  },
  beforeDestroy() {
    if (!this.chart) {
      return;
    }
    this.chart.dispose();
    this.chart = null;
  },
  methods: {
    chinaConfigure() {
      let myChart = echarts.init(document.getElementById('mapChart')); //这里是为了获得容器所在位置    
      window.onresize = myChart.resize;
      myChart.setOption({ // 进行相关配置
        backgroundColor: "rgba(0,0,0,0)",
        tooltip: {}, // 鼠标移到图里面的浮动提示框
        dataRange: {
          show: false,
          min: 0,
          max: 1000,
          text: ['High', 'Low'],
          realtime: true,
          calculable: true,
          color: ['orangered', 'yellow', 'lightskyblue']
        },
        geo: { // 这个是重点配置区
          map: 'china', // 表示中国地图
          roam: true,
          label: {
            normal: {
              show: true, // 是否显示对应地名
              textStyle: {
                color: 'rgba(0,0,0,0.4)'
              }
            }
          },
          itemStyle: {
            normal: {
            //   borderColor: 'rgba(0, 0, 0, 0.2)'
              // areaColor: "rgba(23, 27, 57,0)",
              areaColor: "rgba(0, 141, 255, 1)",
              borderColor: "#1dc199",
              borderWidth: 1
            },
            emphasis: {
              areaColor: null,
              shadowOffsetX: 0,
              shadowOffsetY: 0,
              shadowBlur: 20,
              borderWidth: 0,
              shadowColor: 'rgba(0, 0, 0, 0.5)'
            }
          }
        },
        series: [{
            type: 'scatter',
            coordinateSystem: 'geo' // 对应上方配置
          },
          {
            name: '启动次数', // 浮动框的标题
            type: 'map',
            geoIndex: 0,
            data: [
            //   {
            //   "name": "北京",
            //   "value": 599
            // }, {
            //   "name": "上海",
            //   "value": 142
            // }, {
            //   "name": "黑龙江",
            //   "value": 44
            // }, {
            //   "name": "深圳",
            //   "value": 92
            // }, {
            //   "name": "湖北",
            //   "value": 810
            // }, {
            //   "name": "四川",
            //   "value": 453
            // }
              {
                "name": "陕西",
                "value": 900
              }
            ]
          }
        ]
      });
      let that = this;
      setTimeout(() => {
        myChart.setOption(that.xianOption)
      }, 500);
      myChart.on('click',function(param) {
        // alert(param.code);
        if (param.name=="陕西") {
          myChart.setOption(this.xianOption)
        } else {
          
        }
      })
    },
  }
}
</script>

<style scoped>
.chart {
  width: 100%;
  height: 100%;
}
</style>
