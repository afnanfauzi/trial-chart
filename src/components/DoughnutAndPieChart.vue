<template>
  <div>
    <div class="field is-grouped">
      <div class="control">
        <label class="checkbox">
          2018 Sales
        </label>
      </div>
    </div>

    <doughnut-chart
      :width="50"
      :height="30"
      :labels="['Jan', 'Feb', 'Mar']"
      :datasets="displayedDatasets"
    ></doughnut-chart>
    <pie-chart
      :width="50"
      :height="30"
      :labels="['Jan', 'Feb', 'Mar']"
      :datasets="displayedDatasets"
    ></pie-chart>
    
  </div>
</template>

<script>
import DoughnutChart from './DoughnutChart';
import PieChart from './PieChart';


const datasets = {
  2018: {
    label: '2018 Sales',
    hoverOffset: 4,
    backgroundColor: [
      'rgb(255, 99, 132)',
      'rgb(54, 162, 235)',
      'rgb(255, 205, 86)'
    ],
    data: [300, 50, 100]
  }
};

// const options = {
//   scales: {
//     yAxes: [{
//       ticks: {
//         beginAtZero: true,
//         callback: value => numeral(value).format('$0,0')
//       }
//     }]
//   },
//   tooltips: {
//     mode: 'index',
//     callbacks: {
//       label(tooltipItem, data) {
//         const label = data.datasets[tooltipItem.datasetIndex].label;
//         const value = numeral(tooltipItem.yLabel).format('$0,0');

//         return `${label}: ${value}`;
//       }
//     }
//   }
// };

export default {
  name: 'doughnut-pie',
  datasets,
  components: {
    DoughnutChart,
    PieChart
  },
  data() {
    return {
      selectedYears: [2018]
    };
  },
  computed: {
    displayedDatasets() {
      return this.selectedYears.map(year => datasets[year]);
    }
  }
}
</script>
