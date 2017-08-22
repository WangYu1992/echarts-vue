<template>
  <div id="custom">
    
  </div>
</template>
<script>
  import IEcharts from 'vue-echarts-v3/src/full.vue'

  export default {
    name: 'custom',
    components: {
      IEcharts
    },
    data() {
      return {
        options: {
          title: 'custom chart',
          tooltip: {},
          xAxis: {},
          yAxis: {},
          series: [{
            type: 'custom',
            renderItem: (params, api) => {
              console.log(params, api)
            }
          }]
        }
      }
    }
  }
</script>
<style>
.custom {
  width: 600px;
  height: 600px;
}
</style>
