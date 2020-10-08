
<template>
	<div class="chart">
		<Chart :chartData="chartData" :chartOptions="chartOptions" :chartType="chartType" />
	</div>
</template>

<script>
import Chart from "../Chart";
export default {
	components: {
		Chart,
	},
	data() {
		return {

			chartType: "line",

			chartData: {
				labels: ["Jan1", "Jan2", "Jan3", "Jan4", "Jan5", "Jan6", "Jan7"],
				datasets: [
					{
						label: "This week",
						data: [12, 19, 10, 17, 6, 3, 7],
						backgroundColor: "rgba(224, 248, 255, 0.4)",
						borderColor: "#5cddff",
						lineTension: 0,
						pointBackgroundColor: "#5cddff",
					},
					{
						label: "Last week",
						data: [10, 25, 3, 25, 17, 4, 9],
						backgroundColor: "rgba(241, 225, 197, 0.4)",
						borderColor: "#ffc764",
						lineTension: 0,
						pointBackgroundColor: "#ffc764",
					},
				],
			},

			chartOptions: {
				scales: {
					xAxes: [
						{
							stacked: true,
							gridLines: { 
								display: false,
							 },
						},
					],
					yAxes: [
						{
							gridLines:{
								color:"#ffffff"
							},
							ticks: {
								stepSize: 1,
								callback: function(value, index, values) {
									if (value % Math.round(values[0] / 6) == 0) {
										return value;
									} else if (value === 0) {
										return value;
									}
								},
							},
							
							// stacked: true
						},
					],
				},
				maintainAspectRatio: false,
				legend: {
					labels: {
						boxWidth: 10,
					},
					position: "top",
				},
				animation: {
					duration: 2000,
					easing: "easeInOutQuart",
				},
			
			},
			
		};
	},
};
</script>

<style></style>
