<template>
  <div>
    <Chart :cdata="cdata"/>
  </div>
</template>

<script>
import Chart from './chart.vue'

export default {
  data() {
    return {
      cdata: {
        category: ["1s", "2s", "3s", "4s", "5s", "6s", "7s"],
        uav1: [15, 18.5, 20.9, 16, 25.3, 23, 24.5],
        uav2: [23.5, 14.2, 29.5, 16, 18.2, 8.9, 19.5],
        uav3: [17, 17.6, 19, 25.3, 16.5, 13.3, 17],
        uav4: [24.6, 16.6, 18, 13.5, 20, 36.9, 18.9],
        uav5: [16.3, 23, 18, 19.5, 17.7, 10.6, 20.8]
      }
    };
  },
  components: {
    Chart,
  },
  mounted() {
  },
  methods: {}
};
</script>

<style lang="scss" scoped>
</style>