<script>
	import * as d3 from 'd3';
	
	let { data, xProperty, yProperty, colorProperty, colorMap, margin } = $props();
	
	let chartWidth = $state(400);
	let chartHeight = 400;

	let innerChartWidth = $derived(chartWidth - margin.left - margin.right);
	let innerChartHeight = $derived(chartHeight - margin.top - margin.bottom);

	let xScale = $derived(d3.scaleLinear().domain(d3.extent(data, (row) => row[xProperty])).range([0, innerChartWidth]))
	let yScale = $derived(d3.scaleLinear().domain(d3.extent(data, (row) => row[yProperty])).range([innerChartHeight, 0]))
	let colorScale = $derived(d3.scaleOrdinal().domain(Object.keys(colorMap)).range(Object.values(colorMap)))

	let xTicks = $derived(xScale.ticks());
	let yTicks = $derived(yScale.ticks());
</script>

<div bind:clientWidth={chartWidth}>
	<svg width={chartWidth} height={chartHeight}>
		<g style="transform: translate({margin.left}px, {margin.top}px)">
			<g style="transform: translate(0, {innerChartHeight}px)">
				<line x1="0" y1="0" x2={innerChartWidth} y2="0" stroke="black" stroke-width="4px" />
				{#each xTicks as tick}
					<text x={xScale(tick)} y={25}>{tick}</text>
				{/each}
				<text x={innerChartWidth / 2} y="50px">{xProperty}</text>
			</g>
			<g>
				<line x1="0" y1="0" x2="0" y2={innerChartHeight} stroke="black" stroke-width="4px" />
				{#each yTicks as tick}
					<text x="-35px" y={yScale(tick)}>{tick}</text>
				{/each}
				<g style="transform: translate(-65px, {innerChartHeight / 2 }px) rotate(-90deg)">
					<text>{yProperty}</text>
				</g>
			</g>
			{#each data as row}
				<circle cx={xScale(row[xProperty])} cy={yScale(row[yProperty])} fill={colorScale(row[colorProperty])} r="8px" />
			{/each}
		</g>
	</svg>
</div>

<style>
	svg {
		background-color: white;
	}

	text {
		dominant-baseline: middle;
		text-anchor: middle;
	}

	circle {
		transition: all 500ms ease;
	}
</style>