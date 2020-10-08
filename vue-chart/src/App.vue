<template>
	<div id="app">
		<h2>Vue Charts with Chart.js</h2>
		<div class="d-flex">
				<line-chart/>
				<bar-chart/>
		</div>
	</div>
</template>

<script>
import LineChart from "../src/components/charts/LineChart";
import BarChart from '../src/components/charts/BarChart'
export default {
	name: "App",
	components: {
		LineChart,
		BarChart
	},
};
</script>

<style>
body{
	background-color: #1a1423;
}
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}
.chart{
	width:500px;	
}
.d-flex{
	display: flex;
}
h2{
	color: aliceblue;
	margin-bottom: 30px;
}
</style>
