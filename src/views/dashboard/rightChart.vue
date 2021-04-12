<template>
  <div class="leftChart">
    <el-card shadow="hover" :body-style="{ padding: '20px' }">
      <div slot="header">
        <span>好友结构</span>
      </div>
      <div id="container2"></div>
    </el-card>
  </div>
</template>
<script>
import { Chart, registerShape } from "@antv/g2";
export default {
  data() {
    return {
      chartData: [
        { item: "原始好友", count: 0, percent: 0 },
        { item: "爆粉好友", count: 0, percent: 0 },
        { item: "接粉好友", count: 0, percent: 0 },
      ],
      allNum: 0,
    };
  },
  mounted() {
    this.getAllNum();
    this.initComponent();
  },
  methods: {
    getAllNum() {
      for (const item of this.chartData) {
        this.allNum += item.count;
      }
    },
    initComponent() {
      const chart = new Chart({
        container: "container2",
        autoFit: true,
        height: 300,
      });

      chart.data(this.chartData);
      chart.scale("percent", {
        formatter: (val) => {
          val = val * 100 + "%";
          return val;
        },
      });
      chart.coordinate("theta", {
        radius: 0.75,
        innerRadius: 0.6,
      });
      chart.tooltip({
        showTitle: false,
        showMarkers: false,
        itemTpl:
          '<li class="g2-tooltip-list-item"><span style="background-color:{color};" class="g2-tooltip-marker"></span>{name}: {value}</li>',
      });
      // 辅助文本
      chart
        .annotation()
        .text({
          position: ["50%", "50%"],
          content: "总数",
          style: {
            fontSize: 14,
            fill: "#8c8c8c",
            textAlign: "center",
          },
          offsetY: -20,
        })
        .text({
          position: ["50%", "50%"],
          content: this.allNum,
          style: {
            fontSize: 20,
            fill: "#8c8c8c",
            textAlign: "center",
          },
          offsetX: 0,
          offsetY: 20,
        });
      chart
        .interval()
        .adjust("stack")
        .position("percent")
        .color("item")
        .label("percent", (percent) => {
          if (percent > 0) {
            return {
              content: (data) => {
                return `${data.item}: ${percent * 100}%`;
              },
            };
          }
        })
        .tooltip("item*percent", (item, percent) => {
          percent = percent * 100 + "%";
          return {
            name: item,
            value: percent,
          };
        });
      chart.legend({
        position: "right",
      });
      chart.interaction("element-active");
      chart.render();
    },
  },
};
</script>