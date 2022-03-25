<!--
 * @Author: fanmw
 * @Date: 2022-03-25 11:31:11
 * @Description:表格
-->
<template>
  <div class="chart-container">
    <el-row type="flex" class="row-bg" justify="space-around">
      <el-col :span="10">
        <p>在线人数</p>
        <div class="grid-content bg-purple-light">
          <LineChart id="line2" height="250px" width="100%" :data1="linedata" />
        </div>
      </el-col>
      <el-col :span="10">
        <p>购物总数</p>
        <div class="grid-content bg-purple-light">
          <KeyboardChart id="keychart1" height="250px" width="100%" />
        </div>
      </el-col>
    </el-row>
    <el-row type="flex" class="row-bg" justify="center">
      <el-col :span="20">
        <p>IP面积</p>
        <div class="grid-content bg-purple-light">
          <Area id="keychart2" height="250px" width="100%" />
        </div>
      </el-col>
    </el-row>
    <!-- <chart height="100%" width="100%" /> -->
  </div>
</template>

<script>
import Line from '@/components/Charts/Line'
import KeyboardChart from '@/components/Charts/Keyboard'
import Area from '@/components/Charts/Area'

export default {
  name: 'Keyboard',
  components: { 'LineChart': Line, KeyboardChart, Area },
  data() {
    return {
      linedata: [150, 230, 224, 218, 135, 147, 260]
    }
  }
}
</script>

<style scoped>
.chart-container{
  position: relative;
  width: 100%;
  height: 320px;
}
  .el-row {
    margin-bottom: 20px;
    margin-top: 20px;
  }
  .el-col {
    border-radius: 4px;
  }
  .bg-purple-dark {
    background: #99a9bf;
  }
  .bg-purple {
   border: 1px solid #e5e9f2;
  }
  .bg-purple-light {
    border: 1px solid #e5e9f2;
  }
  .grid-content {
    border-radius: 4px;
    min-height: 200px;
  }
  .row-bg {
    padding: 10px 0;
    background-color: #f9fafc;
  }
</style>

