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
    <div class="totale_box">
      <el-alert
        title="公告：本系统旨在助力企业宣传，规范客服行为，提升企业形象。禁止使用本系统进行电信诈骗、网络赌博、非法传销等一系列违法活动。一经发现，立即封号处理！"
        type="info"
        show-icon
        :closable="false"
      >
      </el-alert>
    </div>
    <div class="char_box">
      <el-row :gutter="20">
        <el-col :xl="12" :lg="24" :offset="0">
          <left-chart></left-chart>
        </el-col>
        <el-col :xl="12" :lg="24" :offset="0">
          <right-chart></right-chart>
        </el-col>
      </el-row>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import leftChart from './leftChart.vue';
import rightChart from './rightChart.vue';
export default {
  name: "Dashboard",
  computed: {},
  components: {
      leftChart,
      rightChart
  },
};
</script>

<style lang="scss" scoped>
.dashboard-container {
  margin: 0 12px;
}
.top {
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
.totale_box {
  margin: 12px 0px;
}
</style>
