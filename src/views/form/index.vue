<template>
  <div id="mailList">
    <headerType :type="5" />
    <div class="mailBox">
      <div class="selectBox marpad show_down">
        <el-row :gutter="8">
          <el-col :span="4" :offset="0">
            <p class="title">所属微信</p>
            <el-select
              v-model="weChartValue"
              size="small"
              placeholder="请选择微信"
            >
              <el-option
                v-for="(item, index) in weChartList"
                :key="index"
                :label="item.label"
                :value="item.value"
              >
              </el-option>
            </el-select>
          </el-col>
          <el-col :span="4" :offset="0">
            <p class="title">标签</p>
            <el-select
              v-model="friendType"
              size="small"
              placeholder="请选择好友标签"
            >
              <el-option
                v-for="(item, index) in friendTypeList"
                :key="index"
                :label="item.label"
                :value="item.value"
              >
              </el-option>
            </el-select>
          </el-col>
          <el-col :span="4" :offset="0">
            <p class="title">来源</p>
            <el-select
              v-model="sourceValue"
              size="small"
              placeholder="请选择是否改密"
            >
              <el-option
                v-for="(item, index) in sourceList"
                :key="index"
                :label="item.label"
                :value="item.value"
              >
              </el-option>
            </el-select>
          </el-col>
          <el-col :span="4" :offset="0">
            <p class="title">单向好友</p>
            <el-select
              v-model="oneFriend"
              size="small"
              placeholder="请选择健康状态"
            >
              <el-option
                v-for="(item, index) in oneFriendList"
                :key="index"
                :label="item.label"
                :value="item.value"
              >
              </el-option>
            </el-select>
          </el-col>
          <el-col :span="4" :offset="0">
            <p class="title">关键词</p>
            <el-input
              v-model="keyWord"
              size="small"
              placeholder="请输入关键词"
            ></el-input>
          </el-col>
          <el-col :span="4" :offset="0">
            <p class="title">操作</p>
            <el-button size="mini" @click="reastFun">重置</el-button>
            <el-button type="primary" size="mini" @click="selectFun"
              >搜索</el-button
            >
          </el-col>
        </el-row>
      </div>
    </div>
    <div class="tabBox show_down marpad">
      <el-table :data="tableData" style="width: 100%">
        <el-table-column type="selection" width="55"> </el-table-column>
        <el-table-column prop="friendMsg" label="好友信息"> </el-table-column>
        <el-table-column prop="weChart" label="所属微信"> </el-table-column>
        <el-table-column prop="type" label="标签"> </el-table-column>
        <el-table-column prop="onIn" label="来源"> </el-table-column>
        <el-table-column prop="time" label="添加时间"> </el-table-column>
        <el-table-column prop="isOne" label="单向好友"> </el-table-column>
        <el-table-column prop="tage" label="拉取标识	"> </el-table-column>
        <el-table-column label="操作">
          <template slot-scope="scope">
            <el-button @click="handleClick(scope.row)" type="text" size="small">
              查看
            </el-button>
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
      keyWord: "",
      weChartValue: "",
      weChartList: [
        {
          label: "全部",
          value: 0,
        },
      ],
      friendType: "",
      friendTypeList: [
        {
          label: "全部",
          value: 0,
        },
        {
          label: "默认标签",
          value: 1,
        },
      ],
      sourceValue: "",
      sourceList: [
        {
          label: "全部",
          value: 0,
        },
        {
          label: "原始好友",
          value: 1,
        },
        {
          label: "爆粉添加",
          value: 2,
        },
        {
          label: "接粉添加",
          value: 3,
        },
      ],
      oneFriend: "",
      oneFriendList: [
        {
          label: "全部",
          value: 0,
        },
        {
          label: "是",
          value: 1,
        },
        {
          label: "否",
          value: 2,
        },
      ],
      tableData: [
        {
          id: 1,
          friendMsg: "sss-33",
          weChart: "ss-eee",
          type: "标签1",
          onIn: "爆粉",
          time: "2020-12-12",
          isOne: "否",
          tage: "无",
        },
      ],
      currentPage2: 1,
    };
  },
  methods: {
    reastFun() {
      this.weChartValue = "";
      this.friendType = "";
      this.sourceValue = "";
      this.oneFriend = "";
      this.keyWord = "";
    },
    selectFun() {
      console.log("搜索");
    },
    handleClick(row) {
      console.log(row);
    },
    handleSizeChange() {},
    handleCurrentChange() {},
  },
};
</script>
<style lang="scss" scoped>
.selectBox {
  .title {
    font-size: 14px;
  }
  .el-select {
    width: 100%;
  }
}
.pageBox {
  text-align: right;
  margin-top: 10px;
}
</style>