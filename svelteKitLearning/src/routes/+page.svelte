<!-- <script>
	const colors = [
  "#FF5733", "#FFC300", "#C70039", "#900C3F", "#581845", "#FF1E56", "#FF931E", "#FFCC29", "#FF3838", "#1B9CFC",
  "#60A3BC", "#55E6C1", "#CAD3C8", "#EAECEE", "#8A8A8A", "#6D214F", "#182C61", "#D6A2E8", "#6D214F", "#182C61",
  "#1B9CFC", "#60A3BC", "#55E6C1", "#CAD3C8", "#EAECEE", "#8A8A8A", "#FFC300", "#C70039", "#900C3F", "#581845",
  "#FF1E56", "#FF931E", "#FFCC29", "#FF3838", "#1B9CFC", "#60A3BC", "#55E6C1", "#CAD3C8", "#EAECEE", "#8A8A8A",
  "#6D214F", "#182C61", "#D6A2E8", "#6D214F", "#182C61", "#1B9CFC", "#60A3BC", "#55E6C1", "#CAD3C8", "#EAECEE"
];
	let selected = colors[0];
</script>

<body style= "background-color: hsl(0, 0%, 18%)">
	<h1 style="color: {selected}">Pick a color</h1>

	<div>
		{#each colors as color, i}
			<button
				aria-current={selected === color}
				aria-label={color}
				style="background: {color}"
				on:click={() => (selected = color)}>{i + 1}</button
			>
		{/each}
	</div>
</body>

<style>
	h1 {
		transition: color 0.2s;	
        text-align: center;
	}

	div {
		display: grid;
		grid-template-columns: repeat(10, 1fr);
		grid-gap: 5px;        
		max-width: 800px;	        
	}

	button {
		aspect-ratio: 1;
		border-radius: 50%;
		background: var(--color, #fff);
		transform: translate(-2px, -2px);
		filter: drop-shadow(2px 2px 3px rgba(0, 0, 0, 0.2));
		transition: all 0.1s;
	}

	button[aria-current='true'] {
		transform: none;
		filter: none;
		box-shadow: inset 3px 3px 4px rgba(0, 0, 0, 0.2);
        border-color: green;
	}
</style>

 <script>
	import Thing from './Thing.svelte';

	let things = [
		{ id: 1, name: 'apple' },
		{ id: 2, name: 'banana' },
		{ id: 3, name: 'carrot' },
		{ id: 4, name: 'doughnut' },
		{ id: 5, name: 'egg' }
	];

	function handleClick() {
		things = things.slice(1);
	}
</script>

<button on:click={handleClick}>
	Remove first thing
</button>

{#each things as thing (thing.id)}
	<Thing name={thing.name} />
{/each} --> 

<script>
	let m = { x: 0, y: 0 };
</script>

<div
	on:pointermove={(e) => {
		m = { x: e.clientX, y: e.clientY };
	}}
>
	The pointer is at {m.x} x {m.y}
</div>

<style>
	div {
		position: fixed;
		left: 0;
		top: 0;
		width: 100%;
		height: 100%;
		padding: 1rem;
	}
</style>
