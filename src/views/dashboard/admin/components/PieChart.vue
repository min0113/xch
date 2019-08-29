<template>
  <div :class="className" :style="{height:height,width:width}" />
</template>

<script>
import echarts from 'echarts'
require('echarts/theme/macarons') // echarts theme
import resize from './mixins/resize'

var  dataList = [
                  {value:335, name:'商城订单',value1:"38%"},
                  {value:310, name:'课程订单',value1:"22%"},
                  {value:234, name:'VIP 订单',value1:"7%"}
                
              ]

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
          tooltip: {
                trigger: 'item',
                formatter: "{a} <br/>{b}: {c} ({d}%)"
            },
        backgroundColor:'#ffffff',
        
         title:[
         {
              text: '销售额',
              x: '2.5%',
              y:'7%',
              textStyle:{
                color:"#000000",
                fontSize:'60%',
                fontWeight:900

              }


        },
        {
          text:'销售额',
          x:'19%',
          y:'40%',
          subtext: '¥'+123+','+224,
          textStyle:{
            fontSize:'60%',
            color:'#909399'
          },
          subtextStyle:{
            fontSize:'130%',
            color:'black',

          },
          textAlign:"center",
          x:'25%',
          y:'44%'
        }
        ],
       color:['#FACC14','#F04864','#8543E0'],

     legend: {
         // type:'scroll',
         icon:"circle",
         orient: 'vertical',
         x: 'left',
         left:'50%',
         top:'30%',
         align:'auto',
         itemWidth:5,
         itemHeight:5,
         formatter: function (name) {
           for(var i=0; i<dataList.length;i++){
            if(dataList[i].name == name){
              return name + "{a| |} {b|"+dataList[i].value1+"} {x|"+'¥'+dataList[i].value+"}";
            }
           }
           

        },
        textStyle:{
          fontSize:9,



          rich: {
            a:{
              color:'#D9D9D9',
              lineHeight:20,
              width:10,
              itemGap:20
             },
            b:{
              color:'#606266',
              fontSize:9,
              width:20,

            },
            x:{  
              color:"#000000",
              fontSize:9,
               width:30,
                padding:[0,0,0,10],

            }
              
          }
        }
    
      
     },
      series : [
          {
              name: '销售额',
              type: 'pie',
              // radius : '55%',
             // center: ['40%', '50%'],
            center: ["25%", "50%"],
            radius: ["40%", "58%"],
             
              data:[
                  {value:335, name:'商城订单'},
                  {value:310, name:'课程订单'},
                  {value:234, name:'VIP 订单'}
                
              ],
              itemStyle: {
                  emphasis: {
                      shadowBlur: 5,
                      shadowOffsetX: 0,
                      shadowColor: 'rgba(0, 0, 0, 0.5)'
                  }
              },
              itemStyle: {
                  normal: {
                      label:{ 
                            show: false, 
                             position:'inside',
                           // formatter: '{b} : {c} ({d}%)' 
                        },
                         borderColor: '#ffffff',
                        borderWidth: 5,
                  },
                    //labelLine :{show:true}
              }
          }
      ]
  }
        
     )
    }
  }
}
</script>
