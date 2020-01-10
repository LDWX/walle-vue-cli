<template>
  <div class="wrapper">
    hello world
    <div>{{msg}}</div>
    <div class="title">
      <!-- {{BLs}} -->
    </div>
    <h1>长度表</h1>
    <div id="fishLengthChart" style="width: 100%; height: 500px;"></div>
    <h1>体重表</h1>
    <div id="fishWeightChart" style="width: 100%; height: 500px;"></div>
  </div>
</template>
<script>
import fishData from "./fish-data.csv";
import echarts from "echarts";

export default {
  data() {
    return {
      msg: "shenxin",
      name: "",

      Seaons: [""],
      maxLength: 0,
      minLength: 0,
      maxWeight: 0,
      minWeight: 0,

      BLs: {
        Autumn: [],
        Spring: [],
        Summer: [],
        Winter: []
      },
      blXais: [],
      BWs: {
        Autumn: [],
        Spring: [],
        Summer: [],
        Winter: []
      },
      bwXaxis: []
    };
  },
  methods: {
    drawFishLengthChart() {
      const vm = this;
      let chart = echarts.init(document.querySelector("#fishLengthChart"));

      let dataTest = Array(10);
      dataTest[3] = 10;
      dataTest[6] = 90;
      let option = {
        color: ["#ff6666", "#99cc33", "#ff9933", "#336699"],
        tooltip: {
          trigger: "axis",
          axisPointer: {
            type: "shadow"
          }
        },
        legend: {
          data: ["Spring", "Summer", "Autumn", "Winter"]
        },
        toolbox: {
          show: true,
          orient: "vertical",
          left: "right",
          top: "center",
          feature: {
            mark: { show: true },
            dataView: { show: true, readOnly: false },
            magicType: { show: true, type: ["line", "bar", "stack", "tiled"] },
            restore: { show: true },
            saveAsImage: { show: true }
          }
        },
        textStyle: {
          fontFamily: "Times New Roman"
        },
        xAxis: [
          {
            type: "category",
            axisTick: { show: false },
            data: [
              "0-10",
              "11-20",
              "21-30",
              "31-40",
              "41-50",
              "51-60",
              "61-70",
              "71-80",
              "81-90",
              "91-100",
              "101-110",
              "111-120",
              "121-130",
              "131-140",
              "141-150",
              "151-160",
              "161-170",
              "171-180",
              "181-190",
              "191-200",
              "201-210",
              "211-220",
              "221-230",
              "231-240",
              "241-250",
              "251-260",
              "261-270",
              "271-280",
              "281-290",
              "291-300",
              "301-310",
              "311-320",
              "321-330",
              "331-340",
              "341-350",
              "351-360",
              "361-370",
              "371-380",
              "381-390",
              "391-400",
              "401-410"
            ]
          }
        ],
        yAxis: [
          {
            type: "value"
          }
        ],
        series: [
          {
            name: "Spring",
            type: "bar",
            barGap: 0,
            barWidth: 10,
            data: vm.BLs.Spring
          },
          {
            name: "Summer",
            type: "bar",
            barGap: 0,
            barWidth: 10,
            data: vm.BLs.Summer
          },
          {
            name: "Autumn",
            type: "bar",
            barGap: 0,
            barWidth: 10,
            data: vm.BLs.Autumn
          },
          {
            name: "Winter",
            type: "bar",
            barGap: 0,
            barWidth: 10,
            data: vm.BLs.Winter
          }
        ],
        dataZoom: [
          // {
          //   type: "slider",
          //   show: true,
          //   xAxisIndex: [0],
          //   start: 0,
          //   end: 100
          // },
          // {
          //   type: "slider",
          //   show: true,
          //   yAxisIndex: [0],
          //   left: "93%",
          //   start: 0,
          //   end: 100
          // },
          {
            type: "inside",
            xAxisIndex: [0],
            start: 0,
            end: 100
          },
          // {
          //   type: "inside",
          //   yAxisIndex: [0],
          //   start: 0,
          //   end: 100
          // }
        ]
      };

      chart.setOption(option);
    },
    drawFishWeightChart() {
      const vm = this;
      let chart = echarts.init(document.querySelector("#fishWeightChart"));

      let dataTest = Array(10);
      dataTest[3] = 10;
      dataTest[6] = 90;
      let option = {
        color: ["#ff6666", "#99cc33", "#ff9933", "#336699"],
        tooltip: {
          trigger: "axis",
          axisPointer: {
            type: "shadow"
          }
        },
        legend: {
          data: ["Spring", "Summer", "Autumn", "Winter"]
        },
        toolbox: {
          show: true,
          orient: "vertical",
          left: "right",
          top: "center",
          feature: {
            mark: { show: true },
            dataView: { show: true, readOnly: false },
            magicType: { show: true, type: ["line", "bar", "stack", "tiled"] },
            restore: { show: true },
            saveAsImage: { show: true }
          }
        },
        textStyle: {
          fontFamily: "Times New Roman"
        },
        xAxis: [
          {
            type: "category",
            axisTick: { show: false },
            data: [
              "0-10",
              "11-20",
              "21-30",
              "31-40",
              "41-50",
              "51-60",
              "61-70",
              "71-80",
              "81-90",
              "91-100",
              "101-110",
              "111-120",
              "121-130",
              "131-140",
              "141-150",
              "151-160",
              "161-170",
              "171-180",
              "181-190",
              "191-200",
              "201-210",
              "211-220",
              "221-230",
              "231-240",
              "241-250",
              "251-260",
              "261-270",
              "271-280",
              "281-290",
              "291-300",
              "301-310",
              "311-320",
              "321-330",
              "331-340",
              "341-350",
              "351-360",
              "361-370",
              "371-380",
              "381-390",
              "391-400",
              "401-410"
            ]
          }
        ],
        yAxis: [
          {
            type: "value"
          }
        ],
        series: [
          {
            name: "Spring",
            type: "bar",
            barGap: 0,
            barWidth: 10,
            data: vm.BWs.Spring
          },
          {
            name: "Summer",
            type: "bar",
            barGap: 0,
            barWidth: 10,
            data: vm.BWs.Summer
          },
          {
            name: "Autumn",
            type: "bar",
            barGap: 0,
            barWidth: 10,
            data: vm.BWs.Autumn
          },
          {
            name: "Winter",
            type: "bar",
            barGap: 0,
            barWidth: 10,
            data: vm.BWs.Winter
          }
        ],
        dataZoom: [
          // {
          //   type: "slider",
          //   show: true,
          //   xAxisIndex: [0],
          //   start: 0,
          //   end: 100
          // },
          // {
          //   type: "slider",
          //   show: true,
          //   yAxisIndex: [0],
          //   left: "93%",
          //   start: 0,
          //   end: 100
          // },
          {
            type: "inside",
            xAxisIndex: [0],
            start: 0,
            end: 100
          },
          // {
          //   type: "inside",
          //   yAxisIndex: [0],
          //   start: 0,
          //   end: 100
          // }
        ]
      };

      chart.setOption(option);
    },
    queryFishData() {
      const vm = this;
      let len = fishData.length;
      let LspringFilter = vm.numberFilter(vm.BLs.Spring);
      let WspringFilter = vm.numberFilter(vm.BWs.Spring);

      let LsummerFilter = vm.numberFilter(vm.BLs.Summer);
      let WsummerFilter = vm.numberFilter(vm.BWs.Summer);

      let LautumnFilter = vm.numberFilter(vm.BLs.Autumn);
      let WautumnFilter = vm.numberFilter(vm.BWs.Autumn);

      let LwinterFilter = vm.numberFilter(vm.BLs.Winter);
      let WwinterFilter = vm.numberFilter(vm.BWs.Winter);

      for (let i = 1; i < len; i++) {
        // debugger
        let fish = fishData[i];
        switch (fish[1]) {
          case "Spring (Apr.)":
            LspringFilter(Number(fish[2]));
            WspringFilter(Number(fish[3]));
            break;
          case "Summer (Jul.)":
            LsummerFilter(Number(fish[2]));
            WsummerFilter(Number(fish[3]));
            break;
          case "Autumn (Oct.)":
            LautumnFilter(Number(fish[2]));
            WautumnFilter(Number(fish[3]));
            break;
          case "Winter (Jan.)":
            LwinterFilter(Number(fish[2]));
            WwinterFilter(Number(fish[3]));
            break;
        }
      }
      console.log("BLs: ", vm.BLs);
      console.log("BWs: ", vm.BWs);
      vm.drawFishLengthChart();
      vm.drawFishWeightChart();
    },
    getXaxis(arr) {},
    numberFilter(arr) {
      return function(num) {
        let numGroup = Math.floor(num / 10);
        if (!arr[numGroup]) {
          arr[numGroup] = 0;
        }
        ++arr[numGroup];
      };
    }
  },
  mounted() {
    this.queryFishData();
  }
};
</script>
