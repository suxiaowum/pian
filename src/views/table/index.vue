<template>
  <div class="wxList">
    <headerType :type="0"></headerType>
    <div class="selectBox">
      <el-row :gutter="8">
        <el-col :span="4" :offset="0">
          <p class="title">所属分组</p>
          <el-select
            v-model="groundValue"
            size="small"
            placeholder="请选择分组"
          >
            <el-option
              v-for="(item, index) in groundList"
              :key="index"
              :label="item.label"
              :value="item.type"
            >
            </el-option>
          </el-select>
        </el-col>
        <el-col :span="4" :offset="0">
          <p class="title">在线状态</p>
          <el-select
            v-model="onlineValue"
            size="small"
            placeholder="请选择在线状态"
          >
            <el-option
              v-for="(item, index) in onlineList"
              :key="index"
              :label="item.label"
              :value="item.type"
            >
            </el-option>
          </el-select>
        </el-col>
        <el-col :span="4" :offset="0">
          <p class="title">改密状态</p>
          <el-select
            v-model="changePassValue"
            size="small"
            placeholder="请选择是否改密"
          >
            <el-option
              v-for="(item, index) in changePassList"
              :key="index"
              :label="item.label"
              :value="item.type"
            >
            </el-option>
          </el-select>
        </el-col>
        <el-col :span="4" :offset="0">
          <p class="title">健康状态</p>
          <el-select
            v-model="healthyValue"
            size="small"
            placeholder="请选择健康状态"
          >
            <el-option
              v-for="(item, index) in healthyList"
              :key="index"
              :label="item.label"
              :value="item.type"
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
    <div class="tableBox show_down">
      <el-table :data="tableData" style="width: 100%">
        <el-table-column type="selection" width="55"> </el-table-column>
        <el-table-column prop="equipment" label="设备信息"> </el-table-column>
        <el-table-column prop="weChartInfo" label="微信详情"> </el-table-column>
        <el-table-column prop="erCode" label="二维码">
          <template slot-scope="scope">
            <el-button @click="seeErcode(scope.row)" type="text" size="small">
              查看
            </el-button>
          </template>
        </el-table-column>
        <el-table-column prop="wxGrouping" label="微信分组"> </el-table-column>
        <el-table-column prop="healthy" label="健康状态"> </el-table-column>
        <el-table-column prop="online" label="在线状态"> </el-table-column>
        <el-table-column prop="friends" label="好友数"> </el-table-column>
        <el-table-column prop="groupChat" label="群聊数	"> </el-table-column>
        <el-table-column label="操作">
          <template slot-scope="scope">
            <el-button @click="handleClick(scope.row)" type="text" size="small">
              查看
            </el-button>
          </template>
        </el-table-column>
      </el-table>
    </div>
    <el-dialog title="提示" :visible.sync="imgDialog" width="30%">
      <div class="dialogBody">
        <el-image :src="erCode" fit="fill" :lazy="true"></el-image>
      </div>
      <div slot="footer" class="dialog-footer" style="text-align: center">
        <el-button @click="imgDialog = false">关闭</el-button>
      </div>
    </el-dialog>
  </div>
</template>
<style lang="scss" scoped>
.selectBox {
  margin: 12px;
  padding: 12px;
  box-shadow: 0 2px 12px 0 rgb(0 0 0 / 10%);
  .title {
    font-size: 14px;
  }
  .el-select {
    width: 100%;
  }
}
.tableBox {
  padding: 12px;
  margin: 12px;
}
</style>
<script>
import headerType from "@/components/header/index.vue";
export default {
  components: {
    headerType,
  },
  data() {
    return {
      imgDialog: false,
      keyWord: "",
      groundValue: "",
      erCode: "",
      groundList: [
        {
          label: "全部",
          type: "1",
          id: 1,
        },
      ],
      onlineValue: "",
      onlineList: [
        {
          label: "全部",
          type: "0",
        },
        {
          label: "在线",
          type: "1",
        },
        {
          label: "离线",
          type: "2",
        },
      ],
      changePassValue: "",
      changePassList: [
        {
          label: "全部",
          type: "0",
        },
        {
          label: "已改密",
          type: "1",
        },
        {
          label: "未改密",
          type: "2",
        },
      ],
      healthyValue: "",
      healthyList: [
        {
          label: "全部",
          type: "0",
        },
        {
          label: "正常",
          type: "1",
        },
        {
          label: "异常",
          type: "2",
        },
        {
          label: "可验证登录",
          type: "2",
        },
      ],
      tableData: [
        // {
        //   equipment: "iphone6",
        //   weChartInfo: "wx-test",
        //   erCode: "https://fuss10.elemecdn.com/a/3f/3302e58f9a181d2509f3dc0fa68b0jpeg.jpeg",
        //   wxGrouping: "分组a",
        //   healthy: "良好",
        //   online: "在线",
        //   friends: "50",
        //   groupChat: "20",
        // },
      ],
    };
  },
  methods: {
    handleClick(row) {
      console.log(row);
    },
    selectFun() {},
    reastFun() {
      this.groundValue = "";
      this.onlineValue = "";
      this.changePassValue = "";
      this.healthyValue = "";
      this.keyWord = "";
    },
    seeErcode(row) {
      console.log(row);
      this.erCode = row.erCode;
      this.imgDialog = true;
    },
  },
};
</script>