<template>
<!--  <div id="bottomRight">-->
<!--    <div class="bg-color-black">-->
<!--      <div class="d-flex pt-2 pl-2">-->
<!--        <span>-->
<!--          <icon name="chart-area" class="text-icon"></icon>-->
<!--        </span>-->
<!--        <div class="d-flex">-->
<!--          <span class="fs-xl text mx-2">丢包率(%)</span>-->
<!--          <div class="decoration2">-->
<!--            <dv-decoration-2 :reverse="true" style="width:5px;height:6rem;" />-->
<!--          </div>-->
<!--        </div>-->
<!--      </div>-->
<!--      <div>-->
<!--        <BottomRightChart />-->
<!--      </div>-->
<!--    </div>-->
<!--  </div>-->
  <div id="bottomRight">
    <div class="bg-color-black">
      <div class="d-flex pt-2 pl-2">
        <span>
          <icon name="chart-bar" class="text-icon"></icon>
        </span>
        <div class="d-flex">
          <span class="fs-xl text mx-2">丢包率(%)</span>
        </div>
      </div>
      <div>
        <BottomRightChart />
      </div>
    </div>
  </div>
</template>

<script>
import BottomRightChart from "@/components/echart/bottom/bottomRightChart";
export default {
  components: {
    BottomRightChart
  }
};
</script>

<style lang="scss" class>
$box-height: 520px;
$box-width: 100%;
#bottomLeft {
  padding: 20px 16px;
  height: $box-height;
  width: $box-width;
  border-radius: 5px;
  .bg-color-black {
    height: $box-height - 35px;
    border-radius: 10px;
  }
  .text {
    color: #c3cbde;
  }
  .chart-box {
    margin-top: 16px;
    width: 170px;
    height: 170px;
    .active-ring-name {
      padding-top: 10px;
    }
  }
}
</style>