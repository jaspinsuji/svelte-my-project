<script>
	let name='Jaspin';
	let fruitName='Orange';
	const handleChangeFruitName=()=>{
		fruitName='Apple';
	}
	const handleInput=(e)=>{
		fruitName=e.target.value;
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>{fruitName} Fruit </p>
	<button on:click={handleChangeFruitName}>Update Fruit Name</button>
	<!-- <input type="text" value={fruitName} on:input={handleInput}/> -->
	<input type="text" bind:value={fruitName}/>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>