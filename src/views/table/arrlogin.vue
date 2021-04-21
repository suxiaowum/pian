<template>
  <div id="arrlogin">
    <headerType :type="2" />

    <div class="marpad show_down">
      <div class="strps">
        <el-steps :active="active" align-center>
          <el-step title="选择分组"></el-step>
          <el-step title="导入微信号"></el-step>
          <el-step title="完成"></el-step>
        </el-steps>
      </div>
      <div class="selectBox" style="text-align: center" v-if="active == 1">
        <span style="font-size: 14px"> 选择分组： </span>
        <el-select
          v-model="groupId"
          placeholder="选择一个分组"
          size="small"
          @change="groupChange"
        >
          <el-option
            v-for="(item, index) in gropList"
            :key="index"
            :label="item.name"
            :value="item.id"
          >
          </el-option>
        </el-select>
        <span class="addGroup" @click="addGroup = true">
          <i class="el-icon-circle-plus"></i>
        </span>
      </div>
      <div class="next">
        <el-button
          v-if="active < 3"
          style="margin-top: 12px"
          @click="next"
          size="mini"
          :disabled="overState"
          >下一步</el-button
        >
        <el-button
          v-else
          type="primary"
          style="margin-top: 12px"
          @click="over"
          size="mini"
          >完成</el-button
        >
      </div>
    </div>
    <el-dialog
      title="新增分组"
      :visible.sync="addGroup"
      width="30%"
      :before-close="addGroupClose"
    >
      <el-form
        :model="form"
        ref="form"
        :rules="rules"
        label-width="80px"
        :inline="false"
        size="mini"
      >
        <el-form-item label="分组名称" prop="name">
          <el-input v-model="form.name" placeholder="请输入分组名称"></el-input>
        </el-form-item>
      </el-form>

      <span slot="footer" class="dialog-footer">
        <el-button @click="addGroup = false">取 消</el-button>
        <el-button type="primary" @click="addGroup = false">确 定</el-button>
      </span>
    </el-dialog>
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
      groupId: "",
      gropList: [{ id: 1, name: "123" }],
      addGroup: false,
      form: {
        name: "",
      },
      rules: {
        name: [{ required: true, message: "请输入活动名称", trigger: "blur" }],
      },
      active: 1,
      overState: true,
    };
  },
  methods: {
    addGroupClose() {},
    next() {
      if (this.active++ > 2) this.active = 1;
      this.overState = true;
    },
    over() {},
    groupChange() {
      this.overState = false;
    },
  },
};
</script>
<style lang="scss" scoped>
.selectBox {
  text-align: center;
  margin-top: 20px;
}
.addGroup {
  font-size: 32px;
  color: #409eff;
  position: relative;
  top: 5px;
  left: 10px;
}
.next {
  text-align: center;
}
</style>