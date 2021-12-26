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
        <dv-scroll-board class="dv-scr-board" :config="config"/>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      config: {
        header: ['UAV', '坐标(m)', '加速度(m/s)', '高度(m)'],
        data: [
          ['UAV1', '(0,0,2)', '(0,0,9.8)', 2],
          ['UAV2', '(2.02,0,2.1)', '(0,0,9.7)', 2.1],
          ['UAV3', '(0,2,2)', '(0,0,9.8)', 2],
          ['UAV4', '(-2,0,1.9)', '(0,0,9.9)', 1.9],
          ['UAV5', '(0,-2,2)', '(0,0,9.8)', 2],
          ['UAV1', '(0.02,0.01,2)', '(0,0,9.8)', 2],
          ['UAV2', '(1.95,0,2.05)', '(0,0,9.7)', 2.05],
          ['UAV3', '(0,2,2)', '(0,0,9.8)', 2],
          ['UAV4', '(-2,0,1.9)', '(0,0,9.9)', 1.9],
          ['UAV5', '(0,-2,2)', '(0,0,9.8)', 2],
          ['UAV1', '(-0.02,0,2)', '(0,0,9.8)', 2],
          ['UAV2', '(2.03,0,2.1)', '(0,0,9.7)', 2.1],
          ['UAV3', '(0,2,2)', '(0,0,9.8)', 2],
          ['UAV4', '(-2,0,1.9)', '(0,0,9.9)', 1.9],
          ['UAV5', '(0,-2,2)', '(0,0,9.8)', 2]
        ],
        rowNum: 7, //表格行数
        headerHeight: 35,
        headerBGC: '#0f1325', //表头
        oddRowBGC: '#0f1325', //奇数行
        evenRowBGC: '#171c33', //偶数行
        index: true,
        columnWidth: [65],
        align: ['center']
      }
    }
  },
  components: {},
  mounted() {
  },
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
