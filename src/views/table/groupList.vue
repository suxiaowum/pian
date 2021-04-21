<template>
  <div id="gropList">
    <headerType :type="4"></headerType>
    <div class="marpad show_down">
      <el-table :data="tableData" style="width: 100%" border>
        <el-table-column type="selection" width="55"> </el-table-column>
        <el-table-column prop="id" label="编号"> </el-table-column>
        <el-table-column prop="name" label="分组名称"> </el-table-column>
        <el-table-column prop="wxNumber" label="绑定微信数"> </el-table-column>
        <el-table-column prop="customerName" label="绑定客服名称">
        </el-table-column>
        <el-table-column label="操作">
          <template slot-scope="scope">
            <el-button @click="handleClick(scope.row)" type="text" size="small">
              编辑
            </el-button>
            <el-button type="text">绑定客服</el-button>
            <span
              style="
                color: rgba(0, 0, 0, 0.65);
                margin: 0 5px;
                position: relative;
                top: -2px;
              "
              >|</span
            >
            <el-button type="text" style="color: #f56c6c">删除</el-button>
          </template>
        </el-table-column>
      </el-table>
      <div class="pageBox">
        <el-pagination
          @size-change="handleSizeChange"
          @current-change="handleCurrentChange"
          :current-page.sync="currentPage2"
          :page-sizes="[100, 200, 300, 400]"
          :page-size="100"
          layout=" total, sizes, prev, pager, next"
          :total="1000"
        >
        </el-pagination>
      </div>
    </div>
  </div>
</template>
<script>
import headerType from "@/components/header/index.vue";
export default {
  components: {
    headerType,
  },
  data() {
    return {
      tableData: [
        // {
        //   id: "1",
        //   name: "123",
        //   wxNumber: "12",
        //   customerName: "213",
        // },
      ],
    };
  },
  methods: {
    handleClick(row) {
      console.log(row);
    },
  },
};
</script>
<style lang="scss" scoped>
.pageBox {
  text-align: right;
  margin-top: 10px;
}
</style>