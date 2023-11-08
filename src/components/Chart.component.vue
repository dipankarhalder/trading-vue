<template>
  <div class="example">
    <apexcharts width="240" type="donut" :options="options" :series="series"></apexcharts>
  </div>
</template>

<script>
import VueApexCharts from 'vue3-apexcharts'

export default {
  name: 'Chart',
  components: {
    apexcharts: VueApexCharts,
  },
  data: function() {
    return {
      options: {
        dataLabels: {
          enabled: true,
          formatter: function () {},
          dropShadow: {}
        },
      },
      series: [44, 55, 41, 17, 15]
    }
  },
}
</script>
