<template>
  <div class="home">
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
          <div id="aqyh">

          </div>
        </div>
      </div>
      <div class="center">
        <div class="city-box">
          <div id="city"></div>
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
          </div>
          <div class="table-box right">
            <div class="title">
              预警信息列表
            </div>
            <div class="btn-box"></div>
          </div>
        </div>
      </div>
      <div class="right">
        <div class="box">
          <div class="title">非居民用户计量信息</div>
        </div>
        <div class="box"> 
          <div class="title">客户服务信息</div>
        </div>
        <div class="box">
          <div class="title">客户黑名单管理</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import echarts from 'echarts';
// import JSON from 'echarts/map/json/province/shanxi1.json';
export default {
  name: 'home',
  props: {
  },
  data() {
    return {
      echartsObj: '',
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
          left: '13%',
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
          bottom: '15%'
        }
      }
    }
  },
  mounted() {
    let rhaj = echarts.init(document.getElementById('rhaj'));
    rhaj.setOption(this.rhajOption);
    let gxxc = echarts.init(document.getElementById('gxxc'));
    gxxc.setOption(this.gxxcOption);
    let aqyh = echarts.init(document.getElementById('aqyh'));
    aqyh.setOption(this.aqyhOption);
  },
  methods: {

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "./home.scss"
</style>
