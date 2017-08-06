<template>
    <div class="pro">
      <div id="charts">
        <div id="main"  :style="{width:'600px',height:'400px'}"></div>
      </div>
    </div>
</template>

<script>
  // 引入基本模板
  let echarts = require('echarts/lib/echarts')
  // 引入柱状图组件
  require('echarts/lib/chart/bar')
  // 引入提示框和title组件
  require('echarts/lib/component/tooltip')
  require('echarts/lib/component/title')

export default {
  name: 'pro',
  data () {
    return {
      msg: "123"
    }
  },
  mounted (){
    var myChart = echarts.init(document.getElementById('main'));
    myChart.setOption({
      title: { text: 'ECharts 入门示例' },
      tooltip: {},
      xAxis: {
        data: ["衬衫","羊毛衫","雪纺衫","裤子","高跟鞋","袜子"]
      },
      yAxis: {},
      series: [{
        name: '销量',
        type: 'bar',
        data: [5, 20, 36, 10, 10, 20]
      }]
    });

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.navbar{ position:fixed;left:0px; top:70px;height:100%; width:100px;background-color:#000;}
.navbar-box-con{}
.navbar-box-con a{ height:72px;display:block; color:#fff;padding-top:40px;}
</style>
