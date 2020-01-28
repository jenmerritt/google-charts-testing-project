<template>
  <div>
    <!-- <p>{{ activities[0].timeStamps }}</p> -->
    <div>
      <GChart
      type="ScatterChart"
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
  ['Name', 'Date', 'Date', 'Date', 'Date', 'Date', 'Date'],
  ['activity 2', new Date(2019, 1, 6), new Date(2019, 1, 7), new Date(2019, 1, 9), new Date(2019, 1, 12), new Date(2019, 1, 15), new Date(2019, 1, 16)],
  ['activity 1', new Date(2019, 1, 6), new Date(2019, 1, 7), new Date(2019, 1, 8), new Date(2019, 1, 9), new Date(2019, 1, 10), new Date(2019, 1, 11)]
],
  chartOptions: {
      title: 'Habit Name',
      legend: {position: 'none'},
      colors: ['#547AA5'],
      pointSize: 5
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
