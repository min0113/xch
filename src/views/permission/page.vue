<template>
  <div class="app-container" id="directive">
   
    <el-tabs type="border-card">
   <!--  <el-tab-pane>
    
    <span slot="label">首页广告</span>

    <SelectedCourses/>

  </el-tab-pane> -->


  <el-tab-pane label="首页广告">
    <HomeAd/>
  </el-tab-pane>
  <el-tab-pane label="商铺广告">
    <ShopAdvertising/>
  </el-tab-pane>
   <el-tab-pane label="VIP广告">
    <VIPAd/>
  </el-tab-pane>
   <el-tab-pane label="添加广告">
    <AddAd/>
  </el-tab-pane>

</el-tabs>

</div>
</template>

<script>
import permission from '@/directive/permission/index.js' // 权限判断指令
// import checkPermission from '@/utils/permission' // 权限判断函数
// import SwitchRoles from './components/SwitchRoles'
import HomeAd from './components/HomeAd'
import ShopAdvertising from './components/ShopAdvertising'
import VIPAd from './components/VIPAd'
import AddAd from './components/AddAd'

export default {
  name: 'DirectivePermission',
   components: { 
    HomeAd,
    ShopAdvertising,
    VIPAd,
    AddAd 

   },
  // directives: { permission },
  data() {
      return {
      
      }
  },
  methods: {
   
  }
}
</script>

<style lang="scss">
.app-container {
  /deep/ .permission-alert {
    width: 320px;
    margin-top: 15px;
    background-color: #f0f9eb;
    color: #67c23a;
    padding: 8px 16px;
    border-radius: 4px;
    display: inline-block;
  }
  /deep/ .permission-sourceCode {
    margin-left: 15px;
  }
  /deep/ .permission-tag {
    background-color: #ecf5ff;
  }
}
/*重置样式*/
#directive{
  .el-tabs--border-card > .el-tabs__header {
     background-color: #ECE6E1; 
    border-bottom: 1px solid hsl(219, 28%, 90%);
    margin: 0;
}

.el-tabs--border-card > .el-tabs__header .el-tabs__item.is-active {
    color: #000;
    background-color: hsl(0, 0%, 100%);
    border-right-color: #fff;
    border-left-color:  #fff;
}

.el-tabs--border-card > .el-tabs__header .el-tabs__item {
    -webkit-transition: all 0.3s cubic-bezier(0.645, 0.045, 0.355, 1);
    transition: all 0.3s cubic-bezier(0.645, 0.045, 0.355, 1);
    /*border: 1px solid  #ECE6E1;*/
    margin-top: -1px;
     color: #000; 
}
.btn_Add{
  .el-button {
    margin: 1vh;
    padding: 12px 20px;
   
}
}


}


</style>

