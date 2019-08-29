<template>
  <div id="container">
    <div class="demo-input-suffix" style="width: 100vw;">
    广告位置:
  <el-select v-model="value" placeholder="请选择" style="width: 30vw;">
    <el-option
      v-for="item in options"
      :key="item.value"
      :label="item.label"
      :value="item.value">
    </el-option>
  </el-select>
</div>

 <div class="demo-input-suffix" style="width: 100vw;">
   是否启用:
   <el-radio v-model="radio" label="1">启用</el-radio>
  <el-radio v-model="radio" label="2">不启动</el-radio>
</div>

<!--广告图 -->
 <div class="demo-input-suffix" style="width: 100vw;" id="demo-input-suffix">
      广告图:


      <dropzone id="myVueDropzone" url="https://httpbin.org/post"  @dropzone-removedFile="dropzoneR" @dropzone-success="dropzoneS" style="width: 60vw;"/>
  


</div>
<!-- 二级xuan -->


 <div class="demo-input-suffix" style="width: 100vw;">
  <div class="block">
  <span class="demonstration">链接：</span>
 <el-cascader :options="options1" clearable :size="medium" style="width: 60vw;"
 placeholder="请选择分类"

 ></el-cascader>
</div>
     

</div>

 
 <div class="demo-input-suffix" style="width: 120vw;">
   <div class="editor-container"style="width: 40vw; margin-left: 2.6vw;">


      <el-input
  placeholder="请输入链接地址"
  v-model="input"
  clearable>
</el-input>
<p style="width: 50vw;">如需跳转链接链接产品不用选择，展示下面图</p>

</div>



</div>



<div class="demo-input-suffix" style="width: 100vw;">

      <tinymce v-model="content" :height="100"  style="margin-top: 1vh;
      margin-bottom: 1vh; margin-left: 4.5vh;
      width: 60vw">
        </tinymce>
 
    <!-- <div class="editor-content" v-html="content" /> -->
</div>

<el-row>
  <div style="margin-left: 25vw;">
  
    <el-button type="success">确定</el-button>
     <el-button plain>取消</el-button>
     </div>
</el-row>

  </div>


</template>
<script>
  import Dropzone from '@/components/Dropzone'
  import Tinymce from '@/components/Tinymce'
 

  export default {
    components: { Dropzone,Tinymce },
    data() {
      return {
        input: '',
        options: [{
          value: '选项1',
          label: '黄金糕'
        }, {
          value: '选项2',
          label: '双皮奶'
        }, {
          value: '选项3',
          label: '蚵仔煎'
        }, {
          value: '选项4',
          label: '龙须面'
        }, {
          value: '选项5',
          label: '北京烤鸭'
        }],
        value: '',
        radio: '1',
        options1: [{
          value: 'zhinan',
          label: '指南',
          children: [{
            value: 'shejiyuanze',
            label: '设计原则',
          
          }, {
            value: 'daohang',
            label: '导航',
          
          }]
        }, {
          value: 'zujian',
          label: '组件',
          children: [{
            value: 'basic',
            label: 'Basic',
          }, {
            value: 'form',
            label: 'Form',
          }, {
            value: 'data',
            label: 'Data',
          }, {
            value: 'notice',
            label: 'Notice',
          }, {
            value: 'navigation',
            label: 'Navigation',
          }, {
            value: 'others',
            label: 'Others',
          }]
        }, {
          value: 'ziyuan',
          label: '资源',
          children: [{
            value: 'axure',
            label: 'Axure Components'
          }, {
            value: 'sketch',
            label: 'Sketch Templates'
          }, {
            value: 'jiaohu',
            label: '组件交互文档'
          }]
        }],



         content:``
     


        
          
     






        
      }
    },
     methods: {
    dropzoneS(file) {
      console.log(file)
      this.$message({ message: 'Upload success', type: 'success' })
    },
    dropzoneR(file) {
      console.log(file)
      this.$message({ message: 'Delete success', type: 'success' })
    }
  }
  }
</script>

<style lang="scss">
  #container{
    .demo-input-suffix{
      display: block;
      margin-top: 0.7vh;

    }
    .editor-container{
      display: flex;
    }

    #demo-input-suffix.demo-input-suffix{
      display: flex;

    }
  }


  </style>