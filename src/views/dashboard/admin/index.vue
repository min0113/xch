<template>
  <div class="dashboard-editor-container">
    <!-- <github-corner class="github-corner" /> -->

    <!-- <panel-group @handleSetLineChartData="handleSetLineChartData" /> -->

   <!--  <el-row style="background:#fff;padding:16px 16px 0;margin-bottom:32px;">
      <line-chart :chart-data="lineChartData" />
    </el-row> -->

    <!-- <el-row :gutter="32"> -->
     
        
          <Drivider />
       
 
   
      <el-col :xs="24" :sm="24" :lg="15">
        <div class="chart-wrapper">

          <div class="tips_box">
            <div class="tips_box_left" id="tips_box_left">
              <el-tabs v-model="activeName" @tab-click="handleClick">
                 <el-tab-pane label="销售额" name="first">销售额</el-tab-pane>
                  <el-tab-pane label="访问量" name="second">访问量</el-tab-pane>
               </el-tabs>
            </div>
            <div class="tips_box_right">
              <span>今日</span>&nbsp;
              <span class="active">本周</span>&nbsp;
              <span>本月</span>&nbsp;
              <span>全年</span>

            </div>
            
          </div>
          <bar-chart />
        </div>
      </el-col>
    </el-row>

       <el-col :xs="24" :sm="24" :lg="9">
        <div class="chart-wrapper">
            <div class="tips_box">
            <div class="tips_box_left">
             <span style="font-size: 11px; font-weight: 800;">销售类别占比</span>

            </div>
            
          </div>
          <pie-chart />
        </div>
      </el-col>


        <el-col :xs="24" :sm="24" :lg="12">
        <div class="chart-wrapper">
          <div class="tips_box">
             <div class="tips_box_left">
              <span>课程排行</span>
            </div>
            <div class="tips_box_right">
              <span>今日</span>&nbsp;
              <span class="active">本周</span>&nbsp;
              <span>本月</span>&nbsp;
              <span>全年</span>

            </div>

          </div>
          
          <Curriculum/>
        </div>
      </el-col>
       <el-col :xs="24" :sm="24" :lg="12">
        <div class="chart-wrapper">
          <div class="tips_box">
             <div class="tips_box_left">
              <span>专栏排行</span>
            </div>
            <div class="tips_box_right">
              <span>今日</span>&nbsp;
              <span class="active">本周</span>&nbsp;
              <span>本月</span>&nbsp;
              <span>全年</span>

            </div>

          </div>
          
          <Curriculum/>
        </div>
      </el-col>

  <!--   <el-row :gutter="8">
      <el-col :xs="{span: 24}" :sm="{span: 24}" :md="{span: 24}" :lg="{span: 12}" :xl="{span: 12}" style="padding-right:8px;margin-bottom:30px;">
        <transaction-table />
      </el-col>
      <el-col :xs="{span: 24}" :sm="{span: 12}" :md="{span: 12}" :lg="{span: 6}" :xl="{span: 6}" style="margin-bottom:30px;">
        <todo-list />
      </el-col>
      <el-col :xs="{span: 24}" :sm="{span: 12}" :md="{span: 12}" :lg="{span: 6}" :xl="{span: 6}" style="margin-bottom:30px;">
        <box-card />
      </el-col>
    -->
     <!-- </el-row> -->
  </div>
</template>

<script>

import BarChart from './components/BarChart'
import PieChart from './components/PieChart'
import Curriculum from './components/Curriculum'
import SpecialColumn from './components/SpecialColumn'
import Drivider from './components/Drivider'

const lineChartData = {
  newVisitis: {
    expectedData: [100, 120, 161, 134, 105, 160, 165],
    actualData: [120, 82, 91, 154, 162, 140, 145]
  },
  messages: {
    expectedData: [200, 192, 120, 144, 160, 130, 140],
    actualData: [180, 160, 151, 106, 145, 150, 130]
  },
  purchases: {
    expectedData: [80, 100, 121, 104, 105, 90, 100],
    actualData: [120, 90, 100, 138, 142, 130, 130]
  },
  shoppings: {
    expectedData: [130, 140, 141, 142, 145, 150, 160],
    actualData: [120, 82, 91, 154, 162, 140, 130]
  }
}

export default {
  name: 'DashboardAdmin',
  components: {
    BarChart,
    PieChart,
    Curriculum,
    SpecialColumn,
    Drivider
   
  },
  data() {
    return {
      activeName: 'first',
      lineChartData: lineChartData.newVisitis
    }
  },
  methods: {
    handleSetLineChartData(type) {
      this.lineChartData = lineChartData[type]
    },
     handleClick(tab, event) {
        console.log(tab, event);
      }
  }
}
</script>

<style lang="scss">
.dashboard-editor-container {
  padding-left: 1vw;
  position: relative;
  .github-corner {
    position: absolute;
    top: 0px;
    border: 0;
    right: 0;
  }

  .chart-wrapper {
    margin-right: 1vw;
    margin-bottom: 2vh;
    .tips_box{
      width: 100%;
      height: 5vh;
      background-color: #fff;
      border-bottom: solid 1px #ccc;
      line-height: 5vh;
      font-size: 11px;
      display: flex;
      justify-content: space-between;
      .tips_box_left{
        margin-left: 2vw;
        font-weight: 900;



      }
      .tips_box_right{
        margin-right: 2vw

      }

    }
  }
  .active{
    color: #1890FF;
  }
}


  .el-tabs__item {
    padding: 0 20px;
    height: 20px;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
    line-height: 20px;
    display: inline-block;
    list-style: none;
    font-size: 12px !important;
    font-weight: 500;
    color: hsl(220, 3%, 19%);
    position: relative;
}

.el-tabs__item:hover {
    color: #A18369!important;
    cursor: pointer;
}





.el-tabs__active-bar {
    position: absolute;
    bottom: 0;
    left: 0;
    height: 2px;
    background-color: #A18369;
    z-index: 1;
    -webkit-transition: -webkit-transform .3s cubic-bezier(.645,.045,.355,1);
    transition: -webkit-transform .3s cubic-bezier(.645,.045,.355,1);
    transition: transform .3s cubic-bezier(.645,.045,.355,1);
    transition: transform .3s cubic-bezier(.645,.045,.355,1), -webkit-transform .3s cubic-bezier(.645,.045,.355,1);
    transition: transform .3s cubic-bezier(.645,.045,.355,1),-webkit-transform .3s cubic-bezier(.645,.045,.355,1);
    list-style: none;
}
@media (max-width:1024px) {
  .chart-wrapper {
    padding: 8px;
  }
}
</style>
