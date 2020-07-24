<script>
	import ContactCard from './ContactCard.svelte'

	let name = 'Darryl';
	let age = 40
	let image =  'https://yt3.ggpht.com/a/AGF-l7_3TCv8Pdu9QA6k2L3OZ5Ddo_DVS1ttBqn_RQ=s900-c-k-c0xffffffff-no-rj-mo'
	let title = 'Web Dev'
	let description = 'New web developer.'
	let goal = 'Learn Svelte'

	$: uppercaseName = name.toUpperCase()
	$: console.log(name)
	$: if (name === 'Darryl Morley') {
		age = 60
	}

	let incrementAge = () => {
		age += 1;
	}

	const changeName = () => {
		name = 'Darryl Morley'
	}

	const nameInput = (event) => {
		const enteredName = event.target.value;
		name = enteredName;
	}
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {uppercaseName}, my age is {age}</h1>
<button on:click="{incrementAge}">Change Age</button>
<!-- <button on:click="{changeName}">Change Name</button> -->
<!-- <input type="text" value="{name}" on:input="{nameInput}"> -->
<input type="text" bind:value="{name}">
<input type="text" bind:value="{title}">
<input type="text" bind:value="{image}">
<input type="text" bind:value="{description}">
<input type="text" bind:value="{goal}">

<ContactCard 
	userName="{name}" 
	userImage="{image}" 
	jobTitle="{title}" 
	{description}
	courseGoal="{goal}" />