<script>
	import Modal from "./Modal.svelte";
	import AddPerson from "./AddPersonForm.svelte";
	let showModal =false;

	let people = [{
    id:1,
    name: 'Suji',
    location: 'Chennai',
    age:31,
    mobile:9876543210
},
{
    id:2,
    name: 'Arun',
    location: 'Bangalore',
    age:31,
    mobile:1234567890
},
{
    id:3,
    name: 'Halin',
    location: 'Nagercoil',
    age:1,
    mobile:1234567890
}];
const handleClick =(id)=>{
	//Delete the person from the people
	console.log (id);
	people = people.filter((person)=>person.id!=id);
}
const toggleModal =()=>{
	showModal = !showModal;
}
let num=5;
</script>

{#if num>20}
<p>Greater than 20</p>
{:else if num>5}
<p>Greater than 5</p>
{:else}
<p>Not Greater than 5</p>
{/if}

<Modal {showModal} on:click={toggleModal}>
	<AddPerson/>
</Modal>
<main>
	<button on:click={toggleModal}>Open Modal</button>
	{#each people as person(person.id)}
	<div>
		<h4>{person.name}</h4>
		<!-- {#if person.location ==='Nagercoil'}
		<p><strong>Master of the Family</strong></p>
		{/if} -->
		<p>{person.age} years old, {person.location} location</p>
		<button on:click={()=>{handleClick(person.id)}}>delete</button>
	</div>
	{:else}
	<p>There are no people to show ...</p>
	{/each}
	<hr/>

	<div>
		<h4>{people[0].name}</h4>
		<p>{people[0].location}</p>
	</div>
	<div>
		<h4>{people[1].name}</h4>
		<p>{people[1].location}</p>
	</div>
	<div>
		<h4>{people[2].name}</h4>
		<p>{people[2].location}</p>
	</div>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>