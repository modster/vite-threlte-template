<script>
  import { Canvas } from '@threlte/core'
  import Scene from './Scene.svelte'
  	import RedThing from './RedThing.svelte';
	import GreenThing from './GreenThing.svelte';
	import BlueThing from './BlueThing.svelte';

	const options = [
		{ color: 'red', component: RedThing },
		{ color: 'green', component: GreenThing },
		{ color: 'blue', component: BlueThing }
	];

	let selected = options[2];
</script>
<div class="z">

<select bind:value={selected}>
	{#each options as option}
		<option value={option}>{option.color}</option>
	{/each}
</select>

</div>

<Canvas>
<svelte:component this={selected.component} />
</Canvas>
<style>
  .z {
    z-index: 10;
  }
</style>
