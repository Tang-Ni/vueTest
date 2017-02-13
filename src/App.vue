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
        tableData: []
      }
    },
    created() {
    var vm=this
    this.$http.get('../static/json/data.json').then(function(response) {
      vm.tableData = response.data.tableData
        }) .catch(function(response) {
          console.log(response)
        })
    }

  }
</script>
