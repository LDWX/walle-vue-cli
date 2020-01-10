<template>
  <div class="wrapper">
    hello world
    <div>
      {{msg}}
    </div>
    <div class="title">
      <!-- {{BLs}} -->
    </div>
    <div class="fishChart" style="width: 100%; height: 500px;"></div>
  </div>
</template>
<script>
import fishData from './fish-data.csv'

export default {
  data() {
    return {
      msg: 'shenxin',
      name: '',

      Seaons: [
        ''
      ],
      BLs: {
        Autumn: [],
        Spring: [],
        Summer: [],
        Winter: []
      },
      BWs: {
        Autumn: [],
        Spring: [],
        Summer: [],
        Winter: []
      }
    }
  },
  methods: {
    print() {
      this.name = "vue success"
    },
    queryFishData() {
      const vm = this
      let len = fishData.length
      for (let i = 1; i < len; i++) {
        debugger
        let fish = fishData[i]
        switch(fish[1]) {
          case "Autumn (Oct.)":
            vm.BLs.Autumn.push( Number(fish[2]) )
            vm.BWs.Autumn.push( Number(fish[3]) )
            break;
          case "Spring (Apr.)":
            vm.BLs.Spring.push( Number(fish[2]) )
            vm.BWs.Spring.push( Number(fish[3]) )
            break;
          case "Summer (Jul.)":
            vm.BLs.Summer.push( Number(fish[2]) )
            vm.BWs.Summer.push( Number(fish[3]) )
            break;
          case "Winter (Jan.)":
            vm.BLs.Winter.push( Number(fish[2]) )
            vm.BWs.Winter.push( Number(fish[3]) )
            break;            
        }
      }
      console.log(vm.BLs)
    }
  },
  mounted() {
    this.print()
    this.queryFishData()
  }
}
</script>
