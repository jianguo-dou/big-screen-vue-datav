<template>
  <div id="centerLeft1">
    <div class="bg-color-black">
      <div class="d-flex pt-2 pl-2">
        <span>
          <icon name="chart-bar" class="text-icon"></icon>
        </span>
        <div class="d-flex">
          <span class="fs-xl text mx-2">环境检测</span>
          <dv-decoration-3 class="dv-dec-3"/>
        </div>
      </div>
      <div class="bottom-data">
        <!--        <div-->
        <!--            class="item-box mt-2"-->
        <!--            v-for="(item, index) in textData"-->
        <!--            :key="index"-->
        <!--        >-->
        <!--          <div class="d-flex">-->
        <!--            <p class="text" style="text-align: center;">-->
        <!--              {{ item.text }}-->
        <!--            </p>-->
        <!--            <dv-digital-flop class="dv-digital-flop" :config="item.content"/>-->
        <!--          </div>-->
        <!--        </div>-->
        <!--        <div-->
        <!--            class="item-box mt-2"-->
        <!--            v-for="(item, index2) in numberData"-->
        <!--            :key="index2"-->
        <!--        >-->
        <!--          <div class="d-flex">-->
        <!--            <p class="text" style="text-align: center;">-->
        <!--              {{ item.text }}-->
        <!--            </p>-->
        <!--            <dv-digital-flop class="dv-digital-flop" :config="item.number"/>-->
        <!--          </div>-->
        <!--        </div>-->

        <div
            class="item-box mt-2"
        >
          <div class="d-flex-justify">
            <p class="text" style="text-align: left;">
              区域
            </p>
            <p class="text" style="text-align: right;">
              {{ response.data.lives[0].city }}
            </p>
          </div>
          <div class="d-flex-justify">
            <p class="text" style="text-align: left;">
              天气
            </p>
            <p class="text" style="text-align: right;">
              {{ response.data.lives[0].weather }}
            </p>
          </div>
          <div class="d-flex-justify">
            <p class="text" style="text-align: left;">
              温度
            </p>
            <p class="text" style="text-align: right;">
              {{ response.data.lives[0].temperature }}
            </p>
          </div>
          <div class="d-flex-justify">
            <p class="text" style="text-align: left;">
              风向
            </p>
            <p class="text" style="text-align: right;">
              {{ response.data.lives[0].winddirection }}
            </p>
          </div>
          <div class="d-flex-justify">
            <p class="text" style="text-align: left;">
              风力
            </p>
            <p class="text" style="text-align: right;">
              {{ response.data.lives[0].windpower }}
            </p>
          </div>
          <div class="d-flex-justify">
            <p class="text" style="text-align: left;">
              湿度
            </p>
            <p class="text" style="text-align: right;">
              {{ response.data.lives[0].humidity }}
            </p>
          </div>
          <div class="d-flex-justify">
            <p class="text" style="text-align: left;">
              更新时间
            </p>
            <p class="smaller-text" style="text-align: right;">
              {{ response.data.lives[0].reporttime }}
            </p>
          </div>
          <div class="d-flex">
            <p class="smaller-text" style="text-align: left;">
              *数据来源：高德开放平台
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      response: {
        data: {
          status: "1",
          count: "1",
          info: "OK",
          infocode: "10000",
          lives: [
            {
              province: "上海",
              city: "",
              adcode: "310000",
              weather: "阴",
              temperature: "10",
              winddirection: "西",
              windpower: "≤3",
              humidity: "62",
              reporttime: "2022-01-01 15:01:41"
            }
          ]
        }
      },
      timer:null, //定时器名称
    }
  },
  mounted() {
    this.getLiveWeather()
    var that = this;
    that.timer = setInterval(() => {
      setTimeout(this.getLiveWeather, 0)
    }, 1000*600)
  },
  methods: {
    getLiveWeather() {
      var that = this;
      that.$axios({
        methods: "get",
        //接口地址  api-代理+接口端口号之后的其余地址
        url: "https://restapi.amap.com/v3/weather/weatherInfo?key=bbf145d05da0fce5cc8c48cea4d6b292&city=310000&extensions=base&output=JSON"
      }).then(response => {
        //验证数据是否获取到
        that.response = response;
        console.log(that.response);
      })
    }
  },
  beforeDestroy(){
    clearInterval(this.timer);
    this.timer = null;
  }
}
</script>

<style lang="scss" scoped>
$box-width: 300px;
$box-height: 410px;

#centerLeft1 {
  padding: 16px;
  height: $box-height;
  width: $box-width;
  border-radius: 10px;

  .bg-color-black {
    height: $box-height - 30px;
    border-radius: 10px;
  }

  .text {
    color: #c3cbde;
  }

  .smaller-text {
    color: #c3cbde;
    font-size: 16px;
  }

  .dv-dec-3 {
    position: relative;
    width: 100px;
    height: 20px;
    top: -3px;
  }

  .d-flex-justify {
    display: flex;
    flex-direction:row;
    justify-content : space-between;
    margin: 10px 0px 10px 0px;
  }

  .bottom-data {
    .item-box {
      & > div {
        padding-right: 5px;
      }

      font-size: 20px;
      float: right;
      position: relative;
      width: 100%;
      color: #d3d6dd;

      .dv-digital-flop {
        width: 120px;
        height: 30px;
      }

      p {
        text-align: center;
      }
    }
  }
}
</style>
