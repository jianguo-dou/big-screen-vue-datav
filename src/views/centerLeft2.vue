<!--<template>-->
<!--  <div id="centerLeft1">-->
<!--    <div class="bg-color-black">-->
<!--      <div class="d-flex pt-2 pl-2">-->
<!--        <span>-->
<!--          <icon name="chart-pie" class="text-icon"></icon>-->
<!--        </span>-->
<!--        <div class="d-flex">-->
<!--          <span class="fs-xl text mx-2">地图数据</span>-->
<!--          <dv-decoration-1 class="dv-dec-1" />-->
<!--        </div>-->
<!--      </div>-->
<!--      <div class="d-flex jc-center">-->
<!--        <CenterLeft2Chart />-->
<!--      </div>-->
<!--    </div>-->
<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--import CenterLeft2Chart from "@/components/echart/centerLeft/centerLeft2Chart";-->
<!--export default {-->
<!--  components: {-->
<!--    CenterLeft2Chart-->
<!--  },-->
<!--};-->
<!--</script>-->

<!--<style lang="scss" scoped>-->
<!--#centerLeft1 {-->
<!--  $box-width: 300px;-->
<!--  $box-height: 410px;-->
<!--  padding: 16px;-->
<!--  height: $box-height;-->
<!--  min-width: $box-width;-->
<!--  border-radius: 5px;-->
<!--  .bg-color-black {-->
<!--    height: $box-height - 30px;-->
<!--    border-radius: 10px;-->
<!--  }-->
<!--  .text {-->
<!--    color: #c3cbde;-->
<!--  }-->
<!--  .dv-dec-1 {-->
<!--    position: relative;-->
<!--    width: 100px;-->
<!--    height: 20px;-->
<!--    top: -3px;-->
<!--  }-->
<!--  .chart-box {-->
<!--    margin-top: 16px;-->
<!--    width: 170px;-->
<!--    height: 170px;-->
<!--    .active-ring-name {-->
<!--      padding-top: 10px;-->
<!--    }-->
<!--  }-->
<!--}-->
<!--</style>-->
<template>
  <div id="centerLeft2">
    <div class="bg-color-black">
      <div class="d-flex pt-2 pl-2">
        <span>
          <icon name="chart-line" class="text-icon"></icon>
        </span>
        <div class="d-flex">
          <span class="fs-xl text mx-2">工作状态</span>
        </div>
      </div>
      <div class="d-flex jc-center body-box">
        <dv-scroll-board class="dv-scr-board" :config="config" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      config: {
        header: ['UAV','飞行状态', '通信质量', '电池电量(%)'],
        data: [
          ['UAV1', "<span  class='fly-status-working'>&emsp;正常&emsp;</span>","<span  class='com-quality-excellent'>&emsp;优&emsp;</span>", '55'],
          ['UAV2', "<span  class='fly-status-working'>&emsp;正常&emsp;</span>","<span  class='com-quality-good'>&emsp;良&emsp;</span>", '79'],
          ['UAV3', "<span  class='fly-status-unkownError'>未知异常</span>","<span  class='com-quality-excellent'>&emsp;优&emsp;</span>", '85'],
          ['UAV4', "<span  class='fly-status-lowBattery'>电量不足</span>","<span  class='com-quality-excellent'>&emsp;优&emsp;</span>", '30'],
          ['UAV5', "<span  class='fly-status-working'>&emsp;正常&emsp;</span>","<span  class='com-quality-bad'>&emsp;差&emsp;</span>", '80']
        ],
        rowNum: 5, //表格行数
        headerHeight: 35,
        headerBGC: '#0f1325', //表头
        oddRowBGC: '#0f1325', //奇数行
        evenRowBGC: '#171c33', //偶数行
        index: false,
        columnWidth: [65],
        align: ['center']
      }
    }
  },
  components: {},
  mounted() {},
  methods: {}
}
</script>

<style lang="scss" scoped>
$box-height: 410px;
$box-width: 100%;
#centerLeft2 {
  padding: 16px;
  padding-top: 20px;
  height: $box-height;
  width: $box-width;
  border-radius: 5px;
  .bg-color-black {
    height: $box-height - 30px;
    border-radius: 10px;
  }
  .text {
    color: #c3cbde;
  }
  .body-box {
    border-radius: 10px;
    overflow: hidden;
    .dv-scr-board {
      width: 470px;
      height: 340px;
    }
  }
}
</style>
