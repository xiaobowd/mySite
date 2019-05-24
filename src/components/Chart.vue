<template>
  <div id="container"
       style="height: 800px; width: 600px; border: 2px solid green;"></div>
</template>

<script>
var echarts = require('echarts')

export default {
  name: 'HelloWorld',
  mounted () {
    this.$nextTick(() => {
      let chart = echarts.init(document.getElementById('container'))
      let option = {
        title: {
          text: '过去七日交易额'
        },
        tooltip: {
          trigger: 'axis'
        },
        legend: {
          data: ['交易额', '交易量']
        },
        toolbox: {
          show: true,
          feature: {
            mark: { show: true },
            dataView: { show: true },
            magicType: { show: true, type: ['line', 'bar'] },
            restore: { show: true },
            saveAsImage: { show: true }
          }
        },
        xAxis: [
          {
            type: 'category',
            position: 'bottom',
            boundaryGap: true,
            axisLine: {
              // 轴线
              show: true,
              lineStyle: {
                color: 'green',
                type: 'solid',
                width: 2
              }
            },
            axisTick: {
              // 轴标记
              show: true,
              length: 10,
              lineStyle: {
                color: 'red',
                type: 'solid',
                width: 2
              }
            },
            axisLabel: {
              show: true,
              interval: 'auto', // {number}
              //              rotate: 45,
              margin: 8,
              formatter: '周{value}',
              textStyle: {
                color: 'blue',
                fontFamily: 'sans-serif',
                fontSize: 15,
                fontStyle: 'italic',
                fontWeight: 'bold'
              }
            },
            splitLine: {
              show: true,
              lineStyle: {
                color: '#483d8b',
                type: 'dashed',
                width: 1
              }
            },
            splitArea: {
              show: true,
              areaStyle: {
                color: ['rgba(144,238,144,0.3)', 'rgba(135,200,250,0.3)']
              }
            },
            data: ['一', '二', '三', '四', '五', '六', '日']
          }
        ],
        yAxis: [
          {
            type: 'value',
            position: 'left',
            // min: 0,
            // max: 300,
            // splitNumber: 5,
            boundaryGap: [0, 1],
            axisLine: {
              // 轴线
              show: true,
              lineStyle: {
                color: 'red',
                type: 'dashed',
                width: 2
              }
            },
            axisTick: {
              // 轴标记
              show: true,
              length: 20,
              lineStyle: {
                color: 'green',
                type: 'solid',
                width: 2
              }
            },
            axisLabel: {
              show: true,
              interval: 'auto', // {number}
              //              rotate: -45,
              margin: 18,
              formatter: '{value}元', // Template formatter!
              textStyle: {
                color: '#1e90ff',
                fontFamily: 'verdana',
                fontSize: 10,
                fontStyle: 'normal',
                fontWeight: 'bold'
              }
            },
            splitLine: {
              show: true,
              lineStyle: {
                color: '#483d8b',
                type: 'dotted',
                width: 2
              }
            },
            splitArea: {
              show: true,
              areaStyle: {
                color: ['rgba(205,92,92,0.3)', 'rgba(255,215,0,0.3)']
              }
            }
          },
          {
            type: 'value',
            splitNumber: 10,
            axisLabel: {
              formatter: function (value) {
                // Function formatter
                return value + '笔'
              }
            },
            splitLine: {
              show: false
            }
          }
        ],
        series: [
          {
            name: '交易额',
            type: 'bar',
            itemStyle: {
              normal: {
                color: '#1eb2b5'
              }
            },
            data: [2000, 2300, 2400, 2500, 3100, 2100, 2800]
          },
          {
            name: '交易量',
            type: 'line',
            yAxisIndex: 1,
            itemStyle: {
              normal: {
                color: '#9F79EE'
              }
            },
            data: [20, 30, 40, 50, 50, 40, 70]
          }
        ]
      }
      chart.setOption(option)
    })
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<style scoped>
</style>
