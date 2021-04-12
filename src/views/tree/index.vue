<template>
  <div id="upweChart">
    <headerType :type="1"></headerType>
    <div
      class="formBox show_down marpad"
      style="padding-top: 60px; padding-bottom: 80px"
    >
      <el-row :gutter="20">
        <el-col :span="5" :offset="8">
          <el-form
            :model="form"
            ref="form"
            :rules="rules"
            label-width="120px"
            :inline="false"
            size="small"
            label-position="right"
          >
            <el-form-item label="微信分组：" prop="groupId">
              <el-select
                v-model="form.groupId"
                placeholder="请选择微信分组"
                clearable
                style="width: 100%"
              >
                <el-option
                  v-for="item in groupList"
                  :key="item.id"
                  :label="item.label"
                  :value="item.id"
                >
                </el-option>
              </el-select>
            </el-form-item>
            <el-form-item label="微信账号：" prop="wxId">
              <el-input
                v-model="form.wxId"
                placeholder="请输入微信账号"
                clearable
              ></el-input>
            </el-form-item>
            <el-form-item label="微信账号：" prop="wxPass">
              <el-input
                v-model="form.wxPass"
                placeholder="请输入密码"
                type="password"
                show-password
              ></el-input>
            </el-form-item>
            <el-form-item label="62/A16：" prop="info">
              <el-input
                v-model="form.info"
                placeholder="请输入62/A16"
                type="textarea"
                show-password
                :rows="6"
              ></el-input>
            </el-form-item>
            <el-form-item style="text-align: center">
              <el-button type="primary" @click="onSubmit">登 录</el-button>
            </el-form-item>
          </el-form>
        </el-col>
      </el-row>
      <div class="marpad">
        <el-divider></el-divider>
        <el-row :gutter="20">
          <el-col :span="8" :offset="8">
            <h2>说明</h2>
            <p class="msgTxt">
              选择一个上号分组，微信号登录成功后将绑定至该分组
            </p>
            <p class="msgTxt">
              一次登录一个微信号，请完整填写微信帐号，微信密码，62/A16。
            </p>
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
      groupList: [
        // {
        //   id: 1,
        //   label: "分组",
        // },
      ],
      form: {
        groupId: "",
        wxId: "",
        wxPass: "",
      },
      rules: {
        groupId: [{ required: true, message: "请选择分组", trigger: "change" }],
        wxId: [{ required: true, message: "请输入微信账号", trigger: "blur" }],
        wxPass: [
          { required: true, message: "请输入微信密码", trigger: "blur" },
        ],
        info: [{ required: true, message: "请输入62/A16", trigger: "blur" }],
      },
    };
  },
  methods: {
    onSubmit() {
      console.log("登录");
    },
  },
};
</script>
<style lang="scss" scoped>
.msgTxt {
  color: rgba(0, 0, 0, 0.45);
  margin-bottom: 12px;
  line-height: 22px;
}
</style>