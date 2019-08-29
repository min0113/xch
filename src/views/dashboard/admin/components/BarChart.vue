<template>


  <div :class="className" :style="{height:height,width:width}">

  </div>

</template>

<script>
import echarts from 'echarts'
require('echarts/theme/macarons') // echarts theme
import resize from './mixins/resize'

const animationDuration = 6000

export default {
  mixins: [resize],
  props: {
    className: {
      type: String,
      default: 'chart'
    },
    width: {
      type: String,
      default: '100%'
    },
    height: {
      type: String,
      default: '33vh'
    }
  },
  data() {
    return {
      chart: null
    }
  },
  mounted() {
    this.$nextTick(() => {
      this.initChart()
    })
  },
  beforeDestroy() {
    if (!this.chart) {
      return
    }
    this.chart.dispose()
    this.chart = null
  },
  methods: {
    initChart() {
      this.chart = echarts.init(this.$el, 'macarons')

  this.chart.setOption({
     backgroundColor: '#ffffff',
      color: ['#A18369'],
     title: {
             text: '销售趋势',
              x: '2.5%',
              y:'7%',
              textStyle:{
                color:"#000000",
                fontSize:'9px',
                fontWeight:900

              }


        },
   
    tooltip : {
        trigger: 'axis',
        axisPointer : {            // 坐标轴指示器，坐标轴触发有效
            type : 'shadow'        // 默认为直线，可选为：'line' | 'shadow'
        }
    },
    grid: {
        show:true,
        left: '3%',
        right: '4%',
        bottom: '3%',
        containLabel: true,
        backgroundColor:'#fff'
    },
    xAxis : [
        {
            type : 'category',
            data : ['10月1日', '10月1日', '10月1日', '10月1日', '10月1日', '10月1日', '10月1日','10月1日','10月1日','10月1日'],
            axisTick: {
                alignWithLabel: true
            },
             axisLine:{
        lineStyle: {
          color:"#000000",
        }

       }
        }
    ],
    yAxis : {
       splitLine: {
        lineStyle:{
          type:'dashed',
         

        },
         show: true
       },

       axisLine:{
        show:false,
        lineStyle: {
          color:"#000000"
        }

       },
       axisTick:{
        show:false
       }
    },
    series : [
        {
            name:'直接访问',
            type:'bar',
            barWidth: '40%',
            data:[10, 52, 200, 334, 390, 330, 220, 390, 330, 220],

        }
    ]
      })
    }
  }
}
</script>

<style scoped lang="scss">

  .chart{
    /*border: solid 1px red;*/
    background-color: #fff;
  

  }
  

</style>
