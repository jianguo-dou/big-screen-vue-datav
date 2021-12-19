<template>
  <div id="centerRight1">
    <div class="bg-color-black">
      <div class="d-flex pt-2 pl-2">
        <span>
          <icon name="chart-line" class="text-icon"></icon>
        </span>
        <div class="d-flex">
          <span class="fs-xl text mx-2">位资数据</span>
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
        header: ['UAV','坐标(m)', '加速度(m/s)', '高度(m)'],
        data: [
          ['UAV1', '(1,2,3)','(0.5,0.5,0.5)', "<span  class='colorGrass'>↑5</span>"],
          ['UAV2', '(3,3,3)','(0,1,1)', "<span  class='colorRed'>↓3</span>"],
          ['UAV3', '(3,2,3)','(0.4,0.5,0.5)', "<span  class='colorGrass'>↑10</span>"],
          ['UAV4', '(1,1,1)','(0.5,0.5,0.5)', "<span  class='colorGrass'>↑9</span>"],
          ['UAV5', '(2,1,1)','(0.5,0.5,0.5)', "<span  class='colorGrass'>↑9</span>"],
          ['UAV6', '(3,3,2)','(0.5,0.5,0.5)', "<span  class='colorGrass'>↑6</span>"],
          ['UAV7', '(4,3,1)','(0.5,0.5,0.5)', "<span  class='colorGrass'>↑8</span>"],
          ['UAV8', '(3,3,3)','(0.5,0.5,0.5)', "<span  class='colorRed'>↓4</span>"],
          ['UAV9', '(1,2,1)','(0.5,0.5,0.5)', "<span  class='colorRed'>↓1</span>"],
          ['UAV10', '(2,2,3)','(0.5,0.5,0.5)', "<span  class='colorGrass'>↑7</span>"]
        ],
        rowNum: 7, //表格行数
        headerHeight: 35,
        headerBGC: '#0f1325', //表头
        oddRowBGC: '#0f1325', //奇数行
        evenRowBGC: '#171c33', //偶数行
        index: true,
        columnWidth: [50],
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
#centerRight1 {
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
