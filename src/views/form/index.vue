<template>
  <div id="mailList">
    <headerType :type="3" />
    <div class="mailBox">
      <div class="selectBox">
        <el-row :gutter="8">
          <el-col :span="4" :offset="0">
            <p class="title">所属微信</p>
            <el-select
              v-model="weChartValue"
              size="small"
              placeholder="请选择分组"
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
                :value="item.value"
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
                :value="item.value"
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
      weChartValue: "",
      weChartList: [
        {
          label: "全部",
          value: 0,
        },
      ],
    };
  },
};
</script>