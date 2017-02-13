<template>
  <div>
    <headernav></headernav>
    <el-table :data="tableData" style="width: 100%">
      <el-table-column prop="Name" label="名称" width="180">
      </el-table-column>
      <el-table-column prop="Url" label="地址" width="180">
      </el-table-column>
      <el-table-column prop="Country" label="国家">
      </el-table-column>
    </el-table>
  </div>
</template>
<script>
  import headernav from "components/Headernav.vue"
  export default {
    components: {
      headernav
    },
    data() {
      return {
        tableData:[]
      }
    },
    created () {
      var vm=this
        jQuery.ajax({
          type: 'Get',
          url: '../static/json/data.json',
          success: function (data) {
            vm.tableData = data.tableData
          },
          error: function(data){
            alert("请求错误");
          }
        })
    }

  }
</script>
