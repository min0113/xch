<template>
  <div>
    
<div class="btn_Add">
    <el-button
          size="mini"
          type="primary"
          @click="handleDelete(scope.$index, scope.row)"
          icon="el-icon-edit">
          添加
    </el-button>
   </div>
  
  <el-table
    :data="tableData"
    border
    style="width: 100%">
    <el-table-column
      prop="id"
      label="序号"
      width="50">
    </el-table-column>
    <el-table-column
      prop="name"
      label="名称"
      width="260">
    </el-table-column>
    <el-table-column
      prop="classify"
      label="分类"
      width="60"
      >
    </el-table-column>
    <el-table-column
      prop="price"
      label="价格"
      width="80"
      >
    </el-table-column>
    <el-table-column
      prop="state"
      label="状态"
      width="60"
      >
    </el-table-column>
    <el-table-column
      prop="startTime"
      label="开始时间"
      width="180"
      >
    </el-table-column>
     <el-table-column
      prop="endTime"
      label="结束时间"
      width="150"
      >
    </el-table-column>
    <el-table-column
      prop="createTime"
      label="创建时间"
      width="150"
      >
    </el-table-column>
      <el-table-column
      prop="operation"
      label="操作"
     
      >
        <template slot-scope="scope">
        <el-button
          size="mini"
          @click="handleEdit(scope.$index, scope.row)">编辑</el-button>
        <el-button
          size="mini"
          type="danger"
          @click="handleDelete(scope.$index, scope.row)">删除</el-button>
      </template>
    </el-table-column>
  </el-table>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        
        tableData: [{
          id: '1',
          name: '零基础企业家修炼—第十三届世纪成功论坛',
          classify: '课程',
          price:'199.00元',
          state:'开启',
          startTime:'2019-08-25 22:52:52',
          endTime:'2019-08-25 22:52:52',
          createTime:'2019-08-25 22:52:52'




        }, {
          date: '2016-05-04',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1517 弄'
        }, {
          date: '2016-05-01',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1519 弄'
        }, {
          date: '2016-05-03',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1516 弄'
        }]
      }

    },
       methods: {
      handleEdit(index, row) {
        console.log(index, row);
      },
      handleDelete(index, row) {
        console.log(index, row);
      }
    }
}
</script>

<style lang="scss">
  .el-table {
    font-size: 1rem;
    color: #606266;
   /* -webkit-transform-origin-x: 0;
    -webkit-transform: scale(0.90);*/

}

.el-table__header tr,
  .el-table__header th {
    padding: 0;
    height: 4.5vh;
    background-color: #FAFAFA;
    text-align: center;
}
.el-table__body tr,
  .el-table__body td {
    padding: 0;
    height: 4.5vh;
    text-align: center;
}

.el-table--enable-row-hover .el-table__body tr:hover>td{
background-color: #fff !important;
}
.el-table--enable-row-hover .el-table__body tr:last-child:hover>td{
background-color: #fff!important;
}



  </style>