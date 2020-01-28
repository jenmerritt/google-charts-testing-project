<template>
  <div id="app">
    <ul v-for="activity in activities">
      <li>{{activity.name}}</li>
      <li>{{activity.timeStamps}}</li>
    </ul>
    <div>
      <GChart
      type="BarChart"
    :data="chartData"
    :options="chartOptions"
    />
    </div>
  </div>
</template>

<script>
import ChartsService from '../../services/ChartsService';
import { GChart } from 'vue-google-charts'

export default {
	name: "app",
  props: ['activities'],
	data () {
    return {
      chartData: [
  ['Name', 'Date', 'Date', 'Date'],
  ['Activity 1', new Date(2020, 1, 6), new Date(2020, 1, 7), new Date(2020, 1, 8)],
],
  chartOptions: {
    chart: {
      title: 'Company Performance',
      subtitle: 'Sales, Expenses, and Profit: 2014-2017'
    },
    legend: {position: 'none'}
  }
  }
},
  components: {
    GChart
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
