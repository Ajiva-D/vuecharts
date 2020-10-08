<template>
	<div :class="chartType">
		<canvas></canvas>
	</div>
</template>

<script>
import Chart from "chart.js";

export default {

	props:{
		chartType:String,
		chartData:Object,
		chartOptions:Object
	},

	methods: {
		
		chartConstructor(chartType, chartData, chartOptions) {
			const chartElement = document.querySelector(`.${this.chartType} canvas`);
			const chart = new Chart(chartElement, {
				type: chartType,
				data: chartData,
				options: chartOptions,
			});
		},

	},
	
	mounted(){
		let {chartType,chartData,chartOptions} = this;
		this.chartConstructor(chartType, chartData, chartOptions);
	}

};
</script>

<style>
canvas{
	height: 250px;
}
</style>
