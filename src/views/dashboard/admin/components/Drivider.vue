<template>
	<div class="mixin-components-container" id="divider">
  <el-row>
  	
      <el-card class="box-card">
        <div style="margin-bottom:50px;">
          <el-col :span="4" class="text-center">
            <router-link class="pan-btn blue-btn" to="/documentation/index">
             登录用户
            </router-link>
          </el-col>
          <el-col :span="4" class="text-center">
            <router-link class="pan-btn light-blue-btn" to="/icon/index">
              新增注册
            </router-link>
          </el-col>
          <el-col :span="4" class="text-center">
            <router-link class="pan-btn pink-btn" to="/excel/export-excel">
             新增VIP
            </router-link>
          </el-col>
          <el-col :span="4" class="text-center">
            <router-link class="pan-btn green-btn" to="/table/complex-table">
             新增讲师
            </router-link>
          </el-col>
          <el-col :span="4" class="text-center">
            <router-link class="pan-btn tiffany-btn" to="/example/create">
              新增课程
            </router-link>
          </el-col>
          <el-col :span="4" class="text-center">
            <router-link class="pan-btn yellow-btn" to="/theme/index">
             今日订单数
            </router-link>
          </el-col>
            <el-col :span="4" class="text-center">
            <router-link class="pan-btn tiffany-btn" to="/example/create">
              今日销售额
            </router-link>
          </el-col>
        </div>
      </el-card>
    </el-row>
    </div>
</template>

<script>



</script>
<style lang="scss">
	#divider{
	.el-card.is-always-shadow {
    /* -webkit-box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1); */
    box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
    width: 83.56vw;
    height: 8vh;
   margin-bottom: 1vh;
   margin-top: 1vh;
}
.pan-btn {
  
     padding: 5px 15px; 
   	
}
.el-col-4 {
     width: 14%; 
}
	}
</style>