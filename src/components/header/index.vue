<template>
  <div class="header">
    <div class="header_title">{{ name }}</div>
    <div class="header_btn">
      <el-button
        round
        size="medium"
        @click="gopage(1)"
        v-if="type == 0 || type == 4"
      >
        客服列表
      </el-button>
      <el-button round size="medium" @click="gopage(2)" v-if="type == 0">
        好友列表
      </el-button>
      <el-button round size="medium" @click="gopage(3)" v-if="type == 0">
        群聊列表
      </el-button>
      <span class="line" v-if="type == 0">|</span>
      <el-button round size="medium" @click="gopage(4)" v-if="type == 0">
        登录微信
      </el-button>
      <el-button round size="medium" @click="gopage(5)" v-if="type == 0">
        微信分组
      </el-button>
      <el-button
        round
        size="medium"
        @click="gopage(6)"
        v-if="type == 1 || type == 2 || type == 3"
      >
        分组列表
      </el-button>
      <el-button
        round
        size="medium"
        @click="gopage(7)"
        v-if="type == 1 || type == 2 || type == 3 || type == 4"
      >
        微信列表
      </el-button>
    </div>
  </div>
</template>
<style lang="scss" scoped>
.header {
  padding: 12px;
  display: flex;
  justify-content: space-between;
  background-color: #fff;
  box-shadow: 0 2px 12px 0 rgb(0 0 0 / 10%);
  margin: 12px;
  &_title {
    font-size: 20px;
    font-weight: 600;
    line-height: 32px;
  }
  .line {
    margin: 0 10px;
    color: #c3c3c3;
  }
}
</style>
<script>
export default {
  data() {
    return {
      name: "",
      wxlbBtn: false,
    };
  },
  props: {
    type: Number,
  },
  mounted() {
    switch (this.type) {
      case 0:
        this.name = "微信列表";
        this.wxlbBtn = true;
        break;
      case 1:
        this.name = "登录微信";
        this.wxlbBtn = true;
        break;
      case 2:
        this.name = "批量登录微信";
        this.wxlbBtn = true;
        break;
      case 3:
        this.name = "扫码登录";
        this.wxlbBtn = true;
        break;
      case 4:
        this.name = "微信分组";
        this.wxlbBtn = true;
        break;
      case 5:
        this.name = "好友列表";
        this.wxlbBtn = true;
        break;
      case 6:
        this.name = "群聊列表";
        this.wxlbBtn = true;
        break;
      default:
        break;
    }
  },
  methods: {
    gopage(type) {
      switch (type) {
        case 1:
          console.log("客服列表");
          break;
        case 2:
          console.log("好友列表");
          break;
        case 3:
          console.log("群聊列表");
          break;
        case 4:
          console.log("登录微信");
          break;
        case 5:
          console.log("微信分组");
          break;

        default:
          break;
      }
    },
  },
};
</script>
