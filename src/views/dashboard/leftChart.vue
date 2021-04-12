<template>
  <div class="leftChart">
    <el-card shadow="hover" :body-style="{ padding: '20px' }">
      <div slot="header">
        <span>好友趋势</span>
      </div>
      <div id="container"></div>
    </el-card>
  </div>
</template>
<script>
import { Chart, registerShape } from "@antv/g2";
export default {
  data() {
    return {
      chartData: [
        { year: "04-08", value: 0, name: "爆粉添加" },
        { year: "04-08", value: 0, name: "接粉添加" },
        { year: "04-08", value: 0, name: "累计增长" },
        { year: "04-09", value: 0, name: "爆粉添加" },
        { year: "04-09", value: 0, name: "接粉添加" },
        { year: "04-09", value: 0, name: "累计增长" },
        { year: "04-10", value: 0, name: "爆粉添加" },
        { year: "04-10", value: 0, name: "接粉添加" },
        { year: "04-10", value: 0, name: "累计增长" },
        { year: "04-11", value: 0, name: "爆粉添加" },
        { year: "04-11", value: 0, name: "接粉添加" },
        { year: "04-11", value: 0, name: "累计增长" },
        { year: "04-12", value: 0, name: "爆粉添加" },
        { year: "04-12", value: 0, name: "接粉添加" },
        { year: "04-12", value: 0, name: "累计增长" },
        { year: "04-13", value: 0, name: "爆粉添加" },
        { year: "04-13", value: 0, name: "接粉添加" },
        { year: "04-13", value: 0, name: "累计增长" },
        { year: "04-14", value: 0, name: "爆粉添加" },
        { year: "04-14", value: 0, name: "接粉添加" },
        { year: "04-14", value: 0, name: "累计增长" },
      ],
    };
  },
  mounted() {
    this.initComponent();
  },
  methods: {
    initComponent() {
      const chart = new Chart({
        container: "container",
        autoFit: true,
        height: 300,
      });

      chart.data(this.chartData);
      chart.scale({
        year: {
          range: [0, 1],
        },
        value: {
          min: 0,
          nice: true,
        },
      });

      chart.tooltip({
        showCrosshairs: true, // 展示 Tooltip 辅助线
        shared: true,
      });
      chart.legend({
        position: "top",
      });
      chart.line().position("year*value").label("value").color("name");
      chart.point().position("year*value");

      chart.render();
    },
  },
};
</script>