<template>
  <div id="groupChart">
    <headerType :type="6"></headerType>
    <div class="marpad show_down">
      <el-table :data="tableData" style="width: 100%" border>
        <el-table-column type="selection" width="55"> </el-table-column>
        <el-table-column prop="name" label="群聊名称"> </el-table-column>
        <el-table-column prop="header" label="群头像"> </el-table-column>
        <el-table-column prop="wxNumber" label="群聊人数"> </el-table-column>
        <el-table-column prop="state" label="状态"> </el-table-column>
        <el-table-column prop="wxChart" label="微信"> </el-table-column>
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
        //   header: "1",
        //   name: "123",
        //   wxNumber: "12",
        //   state:"2",
        // },
      ],
      currentPage2: 1,
    };
  },
  methods: {
    handleClick(row) {
      console.log(row);
    },
  },
  handleSizeChange() {},
  handleCurrentChange() {},
};
</script>
<style lang="scss" scoped>
.pageBox {
  text-align: right;
  margin-top: 10px;
}
</style>