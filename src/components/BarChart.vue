<template>
  <div>
    <canvas ref="myChart" id="myChart" width="400" height="400"></canvas>
  </div>
</template>

<script>
// import Chart from 'chart.js';

export default {
	props: {
		chartdata: {
			type: Array,
			default: [],
		},
	},
	watch: {
		// 1
		chartdata(newValue, oldValue) {
			console.log('received');
			this.renderChart();
		},

		// 2
		// chartdata: {
		// 	handler(newValue, oldValue) {
		// 		this.renderChart();
		// 	},
		// 	// immediate: true,
		// },
	},
	methods: {
		renderChart() {
			let ctx = this.$refs.myChart.getContext('2d');
			// var ctx = document.getElementById('myChart').getContext('2d');
			var myChart = new this.$_Chart(ctx, {
				type: 'bar',
				data: {
					labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
					datasets: this.chartdata,
				},
				options: {
					scales: {
						yAxes: [
							{
								ticks: {
									beginAtZero: true,
								},
							},
						],
					},
				},
			});
		},
	},
	// mounted() {
	// 	this.renderChart();
	// },
};
</script>

<style>
</style>
