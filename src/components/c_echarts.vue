<template>
  <div :id="id" :style="{height:height, width:width}"></div>
</template>

<script>
let echarts = require("echarts/lib/echarts");
require("echarts/lib/chart/bar"); //柱状图
// require("echarts/lib/chart/pie"); //饼图
require("echarts/lib/chart/line"); //饼图
//下面的是需要的提示框
require("echarts/lib/component/tooltip");
require("echarts/lib/component/title");
require("echarts/lib/component/legend");

import { GridComponent } from "echarts/components";
echarts.use([GridComponent]);
export default {
  props: ["id", "options", "width", "height"],
  mounted() {
    this.$nextTick(() => {
      this.draw(this.id); //调用
    });
  },
  methods: {
    draw(id) {
      let myChart = echarts.init(document.getElementById(id));
      myChart.setOption(this.options);
    }
  }
};
</script>