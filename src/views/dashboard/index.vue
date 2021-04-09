<template>
  <div class="dashboard-container">
    <div class="top">
      <el-row :gutter="24">
        <el-col :xl="6" :lg="12" :md="24" :offset="0">
          <div class="top_box">
            <el-card class="box-card">
              <div class="box-card_name">
                设备
                <div class="boc_right" style="float: right">
                  <el-tooltip
                    class="item"
                    effect="dark"
                    content="设备统计"
                    placement="top"
                  >
                    <i class="el-icon-warning"></i>
                  </el-tooltip>
                </div>
              </div>

              <div class="top_item_box">
                <div class="top_item">
                  <div class="top_item_name">设备总数</div>
                  <div class="top_item_num">10</div>
                </div>
                <div class="top_item">
                  <div class="top_item_name">正在使用</div>
                  <div class="top_item_num">10</div>
                </div>
                <div class="top_item">
                  <div class="top_item_name">空闲设备</div>
                  <div class="top_item_num">10</div>
                </div>
                <div class="top_item">
                  <div class="top_item_name">过期设备</div>
                  <div class="top_item_num">10</div>
                </div>
              </div>
            </el-card>
          </div>
        </el-col>
        <el-col :xl="6" :lg="12" :md="24" :offset="0">
          <div class="top_box">
            <el-card class="box-card">
              <div class="box-card_name">
                微信
                <div class="boc_right" style="float: right">
                  <el-tooltip
                    class="item"
                    effect="dark"
                    content="微信统计"
                    placement="top"
                  >
                    <i class="el-icon-warning"></i>
                  </el-tooltip>
                </div>
              </div>

              <div class="top_item_box">
                <div class="top_item">
                  <div class="top_item_name">微信总数</div>
                  <div class="top_item_num">10</div>
                </div>
                <div class="top_item">
                  <div class="top_item_name">在线总数</div>
                  <div class="top_item_num">10</div>
                </div>
                <div class="top_item">
                  <div class="top_item_name">正常离线</div>
                  <div class="top_item_num">10</div>
                </div>
                <div class="top_item">
                  <div class="top_item_name">异常离线</div>
                  <div class="top_item_num">10</div>
                </div>
              </div>
            </el-card>
          </div>
        </el-col>
        <el-col :xl="6" :lg="12" :md="24" :offset="0">
          <div class="top_box">
            <el-card class="box-card">
              <div class="box-card_name">
                爆粉
                <div class="boc_right" style="float: right">
                  <el-tooltip
                    class="item"
                    effect="dark"
                    content="爆粉统计"
                    placement="top"
                  >
                    <i class="el-icon-warning"></i>
                  </el-tooltip>
                </div>
              </div>

              <div class="top_item_box">
                <div class="top_item">
                  <div class="top_item_name">发送成功</div>
                  <div class="top_item_num">10</div>
                </div>
                <div class="top_item">
                  <div class="top_item_name">爆粉成功</div>
                  <div class="top_item_num">10</div>
                </div>
                <div class="top_item">
                  <div class="top_item_name">今日发送</div>
                  <div class="top_item_num">10</div>
                </div>
                <div class="top_item">
                  <div class="top_item_name">今日成功</div>
                  <div class="top_item_num">10</div>
                </div>
              </div>
            </el-card>
          </div>
        </el-col>
        <el-col :xl="6" :lg="12" :md="24" :offset="0">
          <div class="top_box">
            <el-card class="box-card">
              <div class="box-card_name">
                接粉
                <div class="boc_right" style="float: right">
                  <el-tooltip
                    class="item"
                    effect="dark"
                    content="接粉统计"
                    placement="top"
                  >
                    <i class="el-icon-warning"></i>
                  </el-tooltip>
                </div>
              </div>

              <div class="top_item_box">
                <div class="top_item">
                  <div class="top_item_name">申请总数</div>
                  <div class="top_item_num">10</div>
                </div>
                <div class="top_item">
                  <div class="top_item_name">成功总数</div>
                  <div class="top_item_num">10</div>
                </div>
                <div class="top_item">
                  <div class="top_item_name">今日申请</div>
                  <div class="top_item_num">10</div>
                </div>
                <div class="top_item">
                  <div class="top_item_name">今日成功</div>
                  <div class="top_item_num">10</div>
                </div>
              </div>
            </el-card>
          </div></el-col
        >
      </el-row>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "Dashboard",
  computed: {
    ...mapGetters(["name"]),
  },
};
</script>

<style lang="scss" scoped>
.top {
   margin: 0 12px;
  &_box {
    height: 102px;
    margin: 12px 0px;
   
    .box-card {
      &_name {
        color: rgba(0, 0, 0, 0.45);
        font-size: 14px;
        line-height: 22px;
      }
      .top_item_box {
        display: flex;
        justify-content: space-around;
      }
      .top_item_name {
        color: rgba(0, 0, 0, 0.65);
        font-size: 14px;
        margin-top: 5px;
      }
      .top_item_num {
        color: rgba(0, 0, 0, 0.65);
        font-size: 14px;
        margin-top: 5px;
      }
    }
  }
}
</style>
