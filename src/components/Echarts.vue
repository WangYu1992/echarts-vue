<template>
  <div class="echarts">
    <i-echarts :option="options"></i-echarts>
  </div>
</template>
<script>
  import IEcharts from 'vue-echarts-v3/src/full.vue'

  export default {
    name: 'table',
    components: {
      IEcharts
    },
    data() {
      return {
        options: {
          title: {
            text: 'Echarts'
          },
          tooltip: {},
          legend: {
            data: ['销量']
          },
          xAxis: {
            name: '商品',
            nameLocation: 'start',
            nameGap: '50',
            boundaryGap: true,
            data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
          },
          yAxis: {},
          series: [{
            name: '销量',
            type: 'bar',
            data: [5, 20, 36, 60, 10, 55]
          }]
        }
      }
    },
    mounted() {
      // this.changeData()
    },
    methods: {
      changeData() {
        let data = []
        for (let i = 0, min = 5, max = 99; i < 6; i++) {
          data.push(Math.floor(Math.random() * (max + 1 - min) + min))
        }
        this.options.series[0].data = data
        setTimeout(this.changeData, 2000)
      }
    }
  }

</script>
<style>
  .echarts {
    width: 800px;
    height: 400px;
  }
</style>