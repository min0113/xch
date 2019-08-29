  <template>
    <el-table
      :data="tableData"
       style="width: 100%;font-size: 9px"
  
       >
      <el-table-column
        prop="ranking"
        label="排行"
        width="100"
        >
      </el-table-column>
      <el-table-column
        prop="curriculum_name"
        label="课程名称"
        width="200">
      </el-table-column>
      <el-table-column
        prop="lecturer_name"
        label="讲师名称">
      </el-table-column>
       <el-table-column
        prop="people_num"
        label="观看人数">
      </el-table-column>
    </el-table>
  </template>

    <script>
    export default {
      data() {
        return {
          tableData: [{
            ranking: '1',
            curriculum_name: '企业家如何自我成长',
            lecturer_name: '企业家',
            people_num:'2012100'

          },{
            ranking: '1',
            curriculum_name: '企业家如何自我成长',
            lecturer_name: '企业家',
            people_num:'2012100'

          }, {
            ranking: '1',
            curriculum_name: '企业家如何自我成长',
            lecturer_name: '企业家',
            people_num:'2012100'

          },{
            ranking: '1',
            curriculum_name: '企业家如何自我成长',
            lecturer_name: '企业家',
            people_num:'2012100'

          }, {
            ranking: '1',
            curriculum_name: '企业家如何自我成长',
            lecturer_name: '企业家',
            people_num:'2012100'

          }, {
            

          }]
        }
      }
    }
  </script>
  <style lang="scss">
.el-table__header tr,
  .el-table__header th {
    padding: 0;
    height: 4.4vh;
    background-color: #FAFAFA;
    text-align: center;
}
.el-table__body tr,
  .el-table__body td {
    padding: 0;
    height: 4.4vh;
    text-align: center;
}


.el-table--enable-row-hover .el-table__body tr:hover>td{
background-color: #FAFAFA !important;
}
.el-table--enable-row-hover .el-table__body tr:last-child:hover>td{
background-color: #fff!important;
}

</style>