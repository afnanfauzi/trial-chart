<template>
  <div class="container">
    <div class="row">
      <div class="col-12 d-flex">
        <div class="col-6">
          <h2>Monthly Sales Line & Bar Chart</h2>
          <monthly-sales-chart></monthly-sales-chart>
        </div>
        <div class="col-6">
          <h2>Monthly Sales Doughnut & Pie Chart</h2>
          <DoughnutAndPieChart></DoughnutAndPieChart>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import MonthlySalesChart from './components/MonthlySalesChart';
import DoughnutAndPieChart from './components/DoughnutAndPieChart';

export default {
  name: 'app',
  components: {
    MonthlySalesChart,
    DoughnutAndPieChart
  }
}
</script>
