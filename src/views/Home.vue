<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <Cecharts id="rcharts_1" height="300px" width="300px" :options="option" />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import Cecharts from "@/components/c_echarts";

export default {
  name: "Home",
  components: {
    // HelloWorld
    Cecharts
  },
  data() {
    return {
      option: {
        legend: {},
        tooltip: {},
        dataset: {
          source: [
            ["product", "新增用户", "新增信用卡", "新增商户"],
            ["Matcha Latte", 43.3, 85.8, 93.7],
            ["Milk Tea", 83.1, 73.4, 55.1],
            ["Cheese Cocoa", 86.4, 65.2, 82.5],
            ["Walnut Brownie", 72.4, 53.9, 39.1]
          ]
        },
        xAxis: { type: "category" },
        yAxis: {},
        // Declare several bar series, each will be mapped
        // to a column of dataset.source by default.
        series: [
          { type: "line", color: "#f96f96" },
          { type: "line", color: "#7794ec" },
          { type: "line", color: "#efaf49" }
        ]
      }
    };
  }
};
</script>
