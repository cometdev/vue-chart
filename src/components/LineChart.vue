<template>
  <div>
    <canvas ref="myChart" id="myChart"></canvas>
  </div>
</template>

<script>
// import Chart from 'chart.js';

export default {
	methods: {
		renderChart() {
			let ctx = this.$refs.myChart.getContext('2d');
			// var ctx = document.getElementById('myChart').getContext('2d');
			var chart = new this.$_Chart(ctx, {
				// The type of chart we want to create
				type: 'line',

				// The data for our dataset
				data: {
					labels: [
						'January',
						'February',
						'March',
						'April',
						'May',
						'June',
						'July',
					],
					datasets: [
						{
							label: 'My First dataset',
							backgroundColor: 'rgb(255, 99, 132)',
							borderColor: 'rgb(255, 99, 132)',
							data: [0, 10, 5, 2, 20, 30, 45],
						},
					],
				},

				// Configuration options go here
				options: {},
			});
		},
	},
	mounted() {
		this.renderChart();
	},
};
</script>

<style>
</style>
