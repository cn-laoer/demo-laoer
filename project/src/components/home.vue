<template>
  <div class="home" id="home" :style="{'transformOrigin':'center top','transform':`scale(${scalseNum},${scalseNum})`}">
    <div class="header">
      <div class="nav-box left">
        <div class="nav active">入户安检情况</div>
        <div class="nav">管线巡检系统</div>
        <div class="nav">安全隐患系统</div>
        <div class="nav">实时监控系统 </div>
      </div>
      <div class="nav-box right">
        <div class="nav">实时报警系统</div>
        <div class="nav">客户服务系统</div>
        <div class="nav">客户黑名单</div>
        <div class="nav">非居民流量</div>
      </div>
    </div>
    <div class="content">
      <div class="left">
        <div class="box">
          <div class="title">入户安检情况</div>
          <div class="title-box">
            <div class="item">
              <div class="name a">
                500
              </div>
              <div class="desc">安检总量（户）</div>
            </div>
            <div class="item">
              <div class="name b">
                500
              </div>
              <div class="desc">已完成量（户）</div>
            </div>
            <div class="item">
              <div class="name c">
                500
              </div>
              <div class="desc">未完成量（户）</div>
            </div>
            <div class="item">
              <div class="name d">
                500
              </div>
              <div class="desc">安检完成率（%）</div>
            </div>
          </div>
          <div id="rhaj"></div>
        </div>
        <div class="box">
          <div class="title">管线巡检信息</div>
          <div id="gxxc"></div>
        </div>
        <div class="box top">
          <div class="title">安全隐患信息</div>
          <div class="title-scroll-box">
            <div class="item-box">
              <div class="item">123</div>
              <div class="item">33</div>
              <div class="item">222</div>
              <div class="item">44</div>
              <div class="item">534</div>
              <div class="item">2321</div>
              <div class="item">233</div>
              <div class="item">2323</div>
              <div class="item">2323</div>
              <div class="item">32</div>
            </div>
          </div>
          <div id="aqyh"></div>
        </div>
      </div>
      <div class="center">
        <div class="city-box">
          <!-- <div class="city" id="dq" ref="dq" v-if="showMap==1"></div> -->
          <!-- <div class="city" id="china" ref="china" v-if="showMap==2"></div> -->
          <!-- <div class="city" id="city" ref="city" v-if="showMap==3"></div> -->
          <vdq class="city" v-if="showMap==1" v-on:hideDqMap="hideDqMapFn"></vdq>
          <vChina class="city" v-if="showMap==2"></vChina>
        </div>
        <div class="time-box">
          <div>{{nowDate}}</div>
          <div>{{nowTime}}  {{nowWeek}}</div>
        </div>
        <div class="city-select-box">
          <div class="city-select">
            <div class="item">陕西省</div> 
            <div class="item">西安市</div>
            <div class="san"></div> 
          </div>
          <div class="select">
            <div class="item active">西安市</div>
            <div class="item">铜川市</div>
            <div class="item">宝鸡市</div>
            <div class="item">咸阳市</div>
            <div class="item">渭南市</div>
            <div class="item">延安市</div>
            <div class="item">汉中市</div>
            <div class="item">榆林市</div>
            <div class="item">安康市</div>
            <div class="item">商洛市</div>
          </div>
        </div>
        <div class="center-box">
          <div class="table-box left">
            <div class="title">
              安全在线监控
            </div>
            <div class="btn-box">
              <div class="btn active">监控列表</div>
              <div class="btn">全部项目</div>
            </div>
            <div class="table">
              <table cellpadding="0" cellspacing="0">
                <thead>
                  <tr>
                    <td>项目名</td>
                    <td>设备数</td>
                    <td>传感器数</td>
                    <td>报警数</td>
                    <td>操作</td>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <td>太白公司</td>
                    <td>12</td>
                    <td>233</td>
                    <td>1234</td>
                    <td>
                      <span class="rad-btn">报警记录</span>
                      <span class="blue-btn">历史数据</span>
                    </td>
                  </tr>
                  <tr>
                    <td>太白公司</td>
                    <td>12</td>
                    <td>233</td>
                    <td>1234</td>
                    <td>
                      <span class="rad-btn">报警记录</span>
                      <span class="blue-btn">历史数据</span>
                    </td>
                  </tr>
                  <tr>
                    <td>太白公司</td>
                    <td>12</td>
                    <td>233</td>
                    <td>1234</td>
                    <td>
                      <span class="rad-btn">报警记录</span>
                      <span class="blue-btn">历史数据</span>
                    </td>
                  </tr>
                  <tr>
                    <td>太白公司</td>
                    <td>12</td>
                    <td>233</td>
                    <td>1234</td>
                    <td>
                      <span class="rad-btn">报警记录</span>
                      <span class="blue-btn">历史数据</span>
                    </td>
                  </tr>
                  <tr>
                    <td>太白公司</td>
                    <td>12</td>
                    <td>233</td>
                    <td>1234</td>
                    <td>
                      <span class="rad-btn">报警记录</span>
                      <span class="blue-btn">历史数据</span>
                    </td>
                  </tr>
                  <tr>
                    <td>太白公司</td>
                    <td>12</td>
                    <td>233</td>
                    <td>1234</td>
                    <td>
                      <span class="rad-btn">报警记录</span>
                      <span class="blue-btn">历史数据</span>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>
          <div class="table-box right">
            <div class="title">
              预警信息列表
            </div>
            <div class="btn-box"></div>
            <div class="table">
              <table cellpadding="0" cellspacing="0"> 
                <thead>
                  <tr>
                    <td>序号</td>
                    <td>报警名称</td>
                    <td>报警数值/报警阈值</td>
                    <td>报警详情</td>
                    <td>报警级别</td>
                    <td>处理标志</td>
                    <td>时间</td>
                    <td>操作</td>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <td>1</td>
                    <td>温度报警</td>
                    <td>15.75/11</td>
                    <td>asdasdsads</td>
                    <td class="red">严重</td>
                    <td class="yel">未处理</td>
                    <td>2010/10/11</td>
                    <td>
                      <span class="btn1"></span>
                      <span class="btn2"></span>
                      <span class="btn3"></span>
                    </td>
                  </tr>
                  <tr>
                    <td>1</td>
                    <td>温度报警</td>
                    <td>15.75/11</td>
                    <td>asdasdsads</td>
                    <td class="red">严重</td>
                    <td class="yel">未处理</td>
                    <td>2010/10/11</td>
                    <td>
                      <span class="btn1"></span>
                      <span class="btn2"></span>
                      <span class="btn3"></span>
                    </td>
                  </tr>
                  <tr>
                    <td>1</td>
                    <td>温度报警</td>
                    <td>15.75/11</td>
                    <td>asdasdsads</td>
                    <td class="red">严重</td>
                    <td class="yel">未处理</td>
                    <td>2010/10/11</td>
                    <td>
                      <span class="btn1"></span>
                      <span class="btn2"></span>
                      <span class="btn3"></span>
                    </td>
                  </tr>
                  <tr>
                    <td>1</td>
                    <td>温度报警</td>
                    <td>15.75/11</td>
                    <td>asdasdsads</td>
                    <td class="red">严重</td>
                    <td class="yel">未处理</td>
                    <td>2010/10/11</td>
                    <td>
                      <span class="btn1"></span>
                      <span class="btn2"></span>
                      <span class="btn3"></span>
                    </td>
                  </tr>
                  <tr>
                    <td>1</td>
                    <td>温度报警</td>
                    <td>15.75/11</td>
                    <td>asdasdsads</td>
                    <td class="red">严重</td>
                    <td class="yel">未处理</td>
                    <td>2010/10/11</td>
                    <td>
                      <span class="btn1"></span>
                      <span class="btn2"></span>
                      <span class="btn3"></span>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>
      <div class="right">
        <div class="box">
          <div class="title">非居民用户计量信息</div>
          <div class="title-scroll-box">
            <div class="item-box">
              <div class="item">123</div>
              <div class="item">33</div>
              <div class="item">222</div>
              <div class="item">44</div>
              <div class="item">534</div>
              <div class="item">2321</div>
              <div class="item">233</div>
              <div class="item">2323</div>
              <div class="item">2323</div>
              <div class="item">32</div>
            </div>
          </div>
          <div id="fjm"></div>
        </div>
        <div class="box">
          <div class="title">客户服务信息</div>
          <div class="table">
              <table cellpadding="0" cellspacing="0" border="1px solid #1467b7">
                <thead>
                  <tr>
                    <td rowspan="2">项目名</td>
                    <td colspan="2">传感器数</td>
                    <td colspan="2">报警数</td>
                    <td colspan="2">操作</td>
                  </tr>
                  <tr>
                    <td>质量</td>
                    <td>服务</td>
                    <td>质量</td>
                    <td>服务</td>
                    <td>质量</td>
                    <td>服务</td>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <td>已处理</td>
                    <td>12</td>
                    <td>233</td>
                    <td>1234</td>
                    <td>222</td>
                    <td>222</td>
                    <td>222</td>
                  </tr>
                  <tr>
                    <td>处理中</td>
                    <td>12</td>
                    <td>233</td>
                    <td>1234</td>
                    <td>222</td>
                    <td>222</td>
                    <td>222</td>
                  </tr>
                  <tr>
                    <td>未处理</td>
                    <td>12</td>
                    <td>233</td>
                    <td>1234</td>
                    <td>222</td>
                    <td>222</td>
                    <td>222</td>
                  </tr>
                  <tr>
                    <td>合计</td>
                    <td>12</td>
                    <td>233</td>
                    <td>1234</td>
                    <td>222</td>
                    <td>222</td>
                    <td>222</td>
                  </tr>
                  <tr class="zj">
                    <td>总计</td>
                    <td colspan="2">12</td>
                    <td colspan="2">233</td>
                    <td colspan="2">111</td>
                  </tr>
                </tbody>
              </table>
            </div>
        </div>
        <div class="box">
          <div class="title">客户黑名单管理</div>
          <div class="title-box">
            <div class="item">
              <div class="name a">
                500
              </div>
              <div class="desc">黑名单总量</div>
            </div>
            <div class="item">
              <div class="name b">
                500
              </div>
              <div class="desc">已处理</div>
            </div>
            <div class="item">
              <div class="name c">
                500
              </div>
              <div class="desc">费用占用（万元）</div>
            </div>
            <div class="item">
              <div class="name d">
                30
              </div>
              <div class="desc">处理完成率（%）</div>
            </div>
          </div>
          <div class="hmd">
            <div id="hmd" class="item"></div>
            <div id="hmd1" class="item"></div>
          </div>
        </div>
      </div>
    </div>
    <!-- <div class="open" @click="scalsePage()"></div> -->
    <div class="open" @click="toggleFullScreen($event)"></div>
  </div>
</template>

<script>
import echarts from 'echarts';
// import 'echarts/map/js/world.js'
// import 'echarts/map/js/china.js'
// import 'echarts-gl'
import vdq from './common/word3d.vue'
import vChina from './common/chinaMap.vue'
// import JSON from 'echarts/map/json/province/shanxi1.json';
export default {
  name: 'home',
  props: {
  },
  components: {
    vdq,
    vChina
  },
  data() {
    return {
      isFullscreen:true,
      showMap: 1,
      scalseNum: 1,
      nowDate: '',
      nowTime: '',
      nowWeek: '',
      echartsObj: '',
      chinaMapObj: '',
      rhajOption: {
        color: ['#00ff00','#ffff00'],
        legend: {
          show: true,
          top: '25px',
          right: '15px',
          textStyle: {
            color: '#9ad3ed',
            fontSize: 10
          }
        },
        tooltip: {
          trigger: 'axis',
          showContent: false
        },
        xAxis: {
          type: 'category',
          splitNumber: '12',
          data: ['1月', '2月', '3月', '4月', '5月', '6月', '7月','8月','9月','10月','11月','12月'],
          axisTick: {
            show: false,
            alignWithLabel: true
          },
          axisLine: {
            show: false,
            lineStyle: {
              color: '#9ad3ed'
            }
          },
          axisLabel: {
            show: true,
            interval: 0
          }
        },
        yAxis: {
          type: 'value',
          axisLine: {
            show: false,
            lineStyle: {
              color: '#9ad3ed'
            }
          },
          splitLine: {
            lineStyle: {
              color: '#9ad3ed'
            }
          },
        },
        series: [
          {
            name:'安检总量',
            type: 'line', smooth: true, seriesLayoutBy: 'row',
            data: [100, 300, 600, 500, 700, 200, 500, 700, 200, 300, 420, 210],
            areaStyle: {
                normal: {
                  color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [{
                      offset: 0,
                      color: '#00ff00'
                  }, {
                      offset: 1,
                      color: '#06105a'
                  }])
                }
            },
          },
          {
            name:'已完成量',
            type: 'line', smooth: true, seriesLayoutBy: 'row',
            data: [130, 700, 200, 800, 500, 200, 90, 880, 100, 500, 700, 200],
            areaStyle: {
                normal: {
                  color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [{
                      offset: 0,
                      color: '#ffff00'
                  }, {
                      offset: 1,
                      color: '#06105a'
                  }])
                }
            },
          }
        ],
        grid: {
          backgroundColor: 'rgba(255,255,255,0)',
          borderColor: '#068fc2',
          shadowColor: 'rgba(0, 0, 0, 0.5)',
          left: '15%',
          bottom: '18%'
        }
      },
      gxxcOption: {
        color: ['#ff00ff'],
        tooltip: {
          trigger: 'axis',
          axisPointer: {
            type: 'cross',
            crossStyle: {
              color: '#999'
            }
          }
        },
        legend: {
          show: true,
          top: '25px',
          right: '15px',
          textStyle: {
            color: '#9ad3ed',
            fontSize: 10
          },
          data:['计划完成数','实际完成数']
        },
        xAxis: [
          {
            type: 'category',
            data: ['1月','2月','3月','4月','5月','6月','7月','8月','9月','10月','11月','12月'],
            axisPointer: {
              type: 'shadow'
            },
            axisLabel: {
              show: true,
              interval: 0,
              lineStyle: {
                color: '#9ad3ed'
              }
            },
            axisLine: {
              show: true,
              lineStyle: {
                color: '#9ad3ed'
              }
            },
            axisTick: {
              show: false,
              alignWithLabel: true
            },
          },
        ],
        yAxis: {
          type: 'value',
          axisLine: {
            show: false,
            lineStyle: {
              color: '#9ad3ed'
            }
          },
          axisTick: {
            show: false,
            alignWithLabel: true
          },
          splitLine: {
            show: true,
            lineStyle: {
              color: '#9ad3ed'
            }
          },
        },
        series: [
          {
            name:'计划完成数',
            type:'bar',
            data:[100, 800, 700, 500, 900, 200, 1000, 700, 200, 300, 420, 210],
            itemStyle: {
              normal: {
                color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [{
                    offset: 0,
                    color: '#f49310'
                }, {offset: 0.5, color: '#f49310'},{
                    offset: 1,
                    color: '#3a1152'
                }])
              }
            },
          },
          {
            name:'实际完成数',
            type:'line',
            data:[130, 700, 200, 800, 500, 200, 90, 880, 100, 500, 700, 200]
          }
        ],
        grid: {
          backgroundColor: 'rgba(255,255,255,0)',
          borderColor: '#068fc2',
          shadowColor: 'rgba(0, 0, 0, 0.5)',
          left: '13%',
          bottom: '15%'
        }
      },
      aqyhOption: {
        color: ['#ff00ff'],
        tooltip: {
          trigger: 'axis',
          axisPointer: {
            type: 'cross',
            crossStyle: {
              color: '#999'
            }
          }
        },
        legend: {
          show: true,
          top: '30px',
          right: '15px',
          textStyle: {
            color: '#9ad3ed',
            fontSize: 10
          },
          data:['已处理隐患量','已发现隐患量']
        },
        xAxis: [
          {
            type: 'category',
            data: ['1月','2月','3月','4月','5月','6月','7月','8月','9月','10月','11月','12月'],
            axisPointer: {
              type: 'shadow'
            },
            axisLabel: {
              show: true,
              interval: 0,
              lineStyle: {
                color: '#9ad3ed'
              }
            },
            axisLine: {
              show: true,
              lineStyle: {
                color: '#9ad3ed'
              }
            },
            axisTick: {
              show: false,
              alignWithLabel: true
            },
          },
        ],
        yAxis: {
          type: 'value',
          axisLine: {
            show: false,
            lineStyle: {
              color: '#9ad3ed'
            }
          },
          axisTick: {
            show: false,
            alignWithLabel: true
          },
          splitLine: {
            show: true,
            lineStyle: {
              color: '#9ad3ed'
            }
          },
        },
        series: [
          {type: 'bar',
            name:'已处理隐患量',
            data:[200, 500, 400, 600, 300, 500, 600, 200, 100, 800, 420, 210],
            itemStyle: {
              normal: {
                color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [{
                    offset: 0,
                    color: '#2d78f3'
                }, {offset: 0.5, color: '#26b6fa'},{
                    offset: 1,
                    color: '#21e6ff'
                }])
              }
            },
          },
          {
            name:'已发现隐患量',
            type:'bar',
            data:[100, 800, 700, 500, 900, 200, 1000, 700, 200, 300, 420, 210],
            itemStyle: {
              normal: {
                color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [{
                    offset: 0,
                    color: '#fff795'
                }, {offset: 0.5, color: '#fff33f'},{
                    offset: 1,
                    color: '#fff103'
                }])
              }
            },
          }
        ],
        grid: {
          backgroundColor: 'rgba(255,255,255,0)',
          borderColor: '#068fc2',
          shadowColor: 'rgba(0, 0, 0, 0.5)',
          left: '13%',
          bottom: '20%'
        }
      },
      fjmOption: {
        color: ['#00e9ff','#0031ff','#1b9530','#044712','#5e2a45','#af6328','#ef8f11'],
        tooltip: {
          trigger: 'item',
        },
        legend: {
          show: false
        },
        series: [
            {
                name:'公司',
                type:'pie',
                selectedMode: 'single',
                radius: ['20%', '30%'],

                label: {
                    normal: {
                        position: 'inner'
                    }
                },
                labelLine: {
                    normal: {
                        show: false
                    }
                },
                data:[
                    {value:335, name:'直达'},
                    {value:679, name:'营销广告'},
                    {value:1548, name:'搜索引擎'}
                ]
            },
            {
                name:'其他',
                type:'pie',
                radius: ['40%', '55%'],
                labelLine: {
                    normal: {
                        show: false
                    }
                },
                data:[
                    {value:335, name:'直达'},
                    {value:310, name:'邮件营销'},
                    {value:234, name:'联盟广告'},
                    {value:135, name:'视频广告'},
                    {value:1048, name:'百度'},
                    {value:251, name:'谷歌'},
                    {value:147, name:'必应'},
                    {value:102, name:'其他'}
                ]
            },
            {
                name:'非居民',
                type:'pie',
                selectedMode: 'single',
                radius: ['0%', '20%'],

                label: {
                    normal: {
                        position: 'inner'
                    }
                },
                labelLine: {
                    normal: {
                        show: false
                    }
                },
                data:[
                    {value:100, name:'非居民'}
                ]
            },
        ],
        grid: {
          backgroundColor: 'rgba(255,255,255,0)',
          left: '15%',
          bottom: '-5%'
        }
      },
      hmdOption: {
        title : {
        },
        tooltip : {
          trigger: 'item',
          formatter: "{a} <br/>{b} : {c} ({d}%)"
        },
        legend: {
          orient: 'vertical',
          left: 'left',
          bottom: '20%',
          data: ['销售1','销售2','销售3','销售4','销售5']
        },
        series : [
          {
            name: '访问来源',
            type: 'pie',
            radius : '55%',
            center: ['50%', '60%'],
            data:[
              {value:335, name:'销售1'},
              {value:310, name:'销售2'},
              {value:234, name:'销售3'},
              {value:135, name:'销售4'},
              {value:1548, name:'销售5'}
            ],
            itemStyle: {
              emphasis: {
                shadowBlur: 10,
                shadowOffsetX: 0,
                shadowColor: 'rgba(0, 0, 0, 0.5)'
              }
            }
          }
        ]
      },
      hmdOption1: {
        title : {
        },
        tooltip : {
          trigger: 'item',
          formatter: "{a} <br/>{b} : {c} ({d}%)"
        },
        legend: {
          orient: 'vertical',
          left: 'left',
          bottom: '20%',
          data: ['销售1','销售2','销售3','销售4','销售5']
        },
        series : [
          {
            name: '访问来源',
            type: 'pie',
            radius : '55%',
            center: ['50%', '60%'],
            data:[
              {value:335, name:'销售1'},
              {value:310, name:'销售2'},
              {value:234, name:'销售3'},
              {value:135, name:'销售4'},
              {value:1548, name:'销售5'}
            ],
            itemStyle: {
              emphasis: {
                shadowBlur: 10,
                shadowOffsetX: 0,
                shadowColor: 'rgba(0, 0, 0, 0.5)'
              }
            }
          }
        ]
      },
      mapChart:{},
                //立体球形纹路
      option :{
        globe: {
          globeRadius: 83,
          baseTexture: '',//贴图 球形和平面的吻合
          silent: true,
          // environment: rgba(0,0,0,0), //背景
          heightTexture: require("../assets/world.jpg"), //地球的整个纹路
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
    //计算缩放比例
    // this.resize_window();
    // window.addEventListener('resize', () => {
    //     this.resize_window();
    // });
    let _that=this;
    window.onresize = function() {
      if (!_that.checkFull()) {
        //要执行的动作
        _that.isFullscreen=true;
      }
    }
    this.setTimer();
    let rhaj = echarts.init(document.getElementById('rhaj'));
    rhaj.setOption(this.rhajOption);
    let gxxc = echarts.init(document.getElementById('gxxc'));
    gxxc.setOption(this.gxxcOption);
    let aqyh = echarts.init(document.getElementById('aqyh'));
    aqyh.setOption(this.aqyhOption);
    let fjm = echarts.init(document.getElementById('fjm'));
    fjm.setOption(this.fjmOption);
    let hmd = echarts.init(document.getElementById('hmd'));
    hmd.setOption(this.hmdOption);
    let hmd1 = echarts.init(document.getElementById('hmd1'));
    hmd1.setOption(this.hmdOption1);
    // this.initMap()
  },
  methods: {
    // initMap(){
    //   const that = this;
    //   this.mapChart = echarts.init(document.createElement('canvas'));
    //   //获取容器并对其初始化
    //   // this.myChart = echarts.init(document.getElementById('dq'))
    //   this.myChart = echarts.init(this.$refs.dq)
    //   //将平面地球和立体球形的纹路重叠
    //   this.mapChart.setOption(this.mapOption)
    //   this.option.globe.baseTexture = this.mapChart
    //   this.myChart.setOption(this.option);
    //   this.myChart.getZr().on('click',function(e){
    //   // this.myChart.on('click',function(e){
    //     alert(JSON.stringify(e));
    //     that.chinaMap();
    //   });
    // },
    //计算缩放比例
    // resize_window() {
    //   let w_height = Number(document.documentElement.clientHeight / 720);
    //   this.scalseNum = w_height;
    // },
    setTimer() {
      setInterval(()=>{
        let now = new Date();
        var year=now.getFullYear(); 
        var month=now.getMonth()+1<10?'0'+(now.getMonth()+1):now.getMonth()+1; 
        var date=now.getDate()<10?'0'+now.getDate():now.getDate(); 
        var hour=now.getHours()<10?'0'+now.getHours():now.getHours();
        var minute=now.getMinutes()<10?'0'+now.getMinutes():now.getMinutes();
        var week=now.getDay();
        // var second=now.getSeconds();
        this.nowDate = year+'年'+month+'月'+date+'日';
        this.nowTime = hour+':'+minute;
        this.nowWeek = '星期'+'日一二三四五六'.charAt(week);
      },1000);
    },
    chinaMap() {
      this.showMap = 2;
      this.myChart={};
      this.chinaMapObj = echarts.init(document.getElementById('china'));
      this.chinaMapObj.setOption({
        backgroundColor: 'rgba(0,0,0,0)',//canvas的背景颜色
        // environment: './bg.png',//背景星空图
        geo3D: { //地图的具体参数
            map: 'china', //地图范围
            shading: 'lambert', //光照带来的明暗
            light: { // 光照相关的设置。在 shading 为 'color' 的时候无效。
                main: { //场景主光源的设置
                    intensity: 5,//主光源的强度
                    shadow: true,//主光源是否投射阴影
                    shadowQuality: 'high',//阴影的质量
                    alpha: 30, //主光源绕 x 轴偏离的角度
                    beta:190 //主光源绕 y 轴偏离的角度
                },
                ambient: { //全局的环境光设置。
                    intensity: 0//环境光的强度
                }
            },
            viewControl: {//用于鼠标的旋转，缩放等视角控制
                distance: 50,//默认视角距离主体的距离
                panMouseButton: 'left',//平移操作使用的鼠标按键
                rotateMouseButton: 'right',//旋转操作使用的鼠标按键
                alpha:50 // 让canvas在x轴有一定的倾斜角度
            },
            postEffect: {//为画面添加高光，景深，环境光遮蔽（SSAO），调色等效果
                enable: true, //是否开启
                SSAO: {//环境光遮蔽
                    radius: 1,//环境光遮蔽的采样半径。半径越大效果越自然
                    intensity: 1,//环境光遮蔽的强度
                    enable: true
                }
            },
            temporalSuperSampling: {//分帧超采样。在开启 postEffect 后，WebGL 默认的 MSAA 会无法使用,分帧超采样用来解决锯齿的问题
                enable: true
            },
            itemStyle: {//三维图形的视觉属性
                color:'#2355ac',
                borderWidth:1,
                borderColor:'#000'
            },
            regionHeight: 2//区域的高度
        }
      });
    },
    hideDqMapFn() {
      this.showMap = 2;
    },
    checkFull() {
      var isFull = document.fullscreenEnabled || window.fullScreen || document.webkitIsFullScreen || document.msFullscreenEnabled;
      if (isFull === undefined) {isFull = false;}
      return isFull
    },
    FullScreen(el){
      if(this.isFullscreen){//退出全屏
        if(document.exitFullscreen){
          document.exitFullscreen()
        }else if( document.mozCancelFullScreen){
          document.mozCancelFullScreen()
        }else if(document.webkitExitFullscreen){
          //改变平面图在google浏览器上面的样式问题
          // $("#canvasPaintArea").css("position","static").css("width","100%");
          // $(".buildingsFloor").css("width","70%");
          // $(".floor-plan").css("width","78%");
          document.webkitExitFullscreen()
        }else if(!document.msRequestFullscreen){
          document.msExitFullscreen()
        }
      }else{    //进入全屏
        if(el.requestFullscreen){
          el.requestFullscreen()
        }else if(el.mozRequestFullScreen){
          el.mozRequestFullScreen()
        }else if(el.webkitRequestFullscreen){
          //改变平面图在google浏览器上面的样式问题
          // $("#canvasPaintArea").css("position","absolute").css("width","94%");
          // $(".buildingsFloor").css("width","98%");
          // $(".floor-plan").css("width","90%");
          el.webkitRequestFullscreen(); 
        }else if(el.msRequestFullscreen){
          this.isFullscreen=true;
          el.msRequestFullscreen()            
        }
      }
    },
    toggleFullScreen(){
      this.isFullscreen=!this.isFullscreen;
      this.FullScreen(document.getElementById("home"));
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "./home.scss"
</style>
