<script>
	import { onMount } from 'svelte';
	import * as d3 from 'd3';

	import ScatterPlot from './ScatterPlot.svelte';

	let data = $state([]);
	let xProperty = $state("weight");
	let yProperty = $state("raceTime");
	let colorProperty = "name";

	let pokeData = $state([])

	onMount(async () => {
		data = await d3.csv('https://raw.githubusercontent.com/gckirchoff/league-of-pigs-data/refs/heads/master/data.csv', (row) => ({
			...row,
			season: +row.season,
			round: +row.round,
			race: +row.race,
			length: +row.length,
			height: +row.height,
			waist: +row.waist,
			weight: +row.weight,
			isMale: row['is male'] === 'TRUE',
			position: +row.position,
			raceTime: +row['race time'],
		}));

		const fetchedPokeData = await d3.json('https://pokeapi.co/api/v2/pokemon?limit=100');
		const allResults = await Promise.all(fetchedPokeData.results.map((pokemon) => d3.json(pokemon.url)))
		const parsedResults = allResults.map((pokemon) => ({
			weight: pokemon.weight,
			height: pokemon.height,
			defense: pokemon.stats[2].base_stat,
			speed: pokemon.stats[5].base_stat,
			type: pokemon.types[0].type.name,
		}))
		pokeData = parsedResults;
	});

	const margin = {
		top: 50,
		right: 50,
		bottom: 70,
		left: 95,
	}

	const colorMap = {
		'ginger hamilton': 'orange',
		'hoshi oinku': 'green',
		'pepper sanchez': 'purple',
		'bear trotsky': 'red',
		'piggy smalls': 'blue',
	}

	const pokeColorMap = {
		fire: 'red',
		grass: 'green',
		water: 'blue',
		dark: 'black',
		rock: 'brown',
		ground: 'beige',
		electric: 'yellow',
		flying: 'grey',
		bug: '#98e336',
		dragon: '#081e70',
		poison: 'purple',
		ghost: '#715fe3',
		fighting: '#bd4317',
		ice: '#62fcde',
		normal: '#849995',
		psychic: 'pink',
	}
</script>

<div>
	<label>
		x property
		<select bind:value={xProperty}>
			<option value="weight">Weight</option>
			<option value="length">Length</option>
		</select>
	</label>

	<label>
		Independent variable
		<select bind:value={yProperty}>
			<option value="raceTime">Race Time</option>
			<option value="position">Position</option>
		</select>
	</label>
</div>

<ScatterPlot {data} {xProperty} {yProperty} {colorProperty} {colorMap} {margin} />
<ScatterPlot data={pokeData} xProperty="weight" yProperty="speed" colorProperty="type" {colorMap} margin={margin} />