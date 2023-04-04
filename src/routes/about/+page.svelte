<svelte:head>
	<title>About</title>
	<meta name="description" content="About this app" />
</svelte:head>

<script lang="ts">
	import agent from '$lib/images/devs/agent.png'
	import cherry from '$lib/images/devs/cherry.png'
	import clearwater from '$lib/images/devs/clearly.png'
	import glitchy from '$lib/images/devs/glitchy.png'
	import hydra from '$lib/images/devs/hydra.png'
	import doodz from '$lib/images/devs/doodz.png'
	import temperz from '$lib/images/devs/temperz.png'
	import waffle from '$lib/images/devs/waffle.png'
	import zed from '$lib/images/devs/zed.png'
	import zelz from '$lib/images/devs/zelz.png'

	let devs: Array<[string, string, string, string]> = [
		[agent, "Agent of Nyarlathotep", "Developer", "does things"],
		[cherry, "cherry donuts", "Developer", "does things"],
		[clearwater, "Clearwater", "Developer", "does things"],
		[glitchy, "Glitchy", "Developer", "does things"],
		[hydra, "Hydra", "Developer", "does things"],
		[doodz, "teamdoodz", "Developer", "does things"],
		[temperz, "Temperz87", "Developer", "does things"],
		[waffle, "Waffle", "Developer", "does things"],
		[zed, "ZedDev", "Developer", "does things"],
		[zelz, "zelzmiy", "Developer", "does things"]
	]

	// i sole this lmao: https://stackoverflow.com/questions/2450954/how-to-randomize-shuffle-a-javascript-array
	devs = devs
		.map(value => ({ value, sort: Math.random() }))
    	.sort((a, b) => a.sort - b.sort)
    	.map(({ value }) => value)

	let devHolder: Element;
	let devBox: Element;
	let rowHolder: Element;

	import { onMount } from 'svelte';

	onMount(() => {
		devHolder = document.getElementById("devHolder") as Element;
		devBox = document.getElementById("devBox") as Element;
		rowHolder = document.getElementById("rowHolder") as Element;

		let currentRow : Element;
		let devCountThisRow: number = 0;

		devs.forEach(dev => {
			if (devCountThisRow == 3 || currentRow == null) {
				currentRow = devHolder.cloneNode(true) as Element;
				console.log(devHolder.children.length);
				rowHolder.appendChild(currentRow);
				devCountThisRow = 0;
			}

			let clone: Element = devBox.cloneNode(true) as Element;
			currentRow.appendChild(clone);

			(<HTMLImageElement>clone.children[0].children[0]).src = dev[0];
			clone.children[0].children[1].textContent = dev[1];
			clone.children[0].children[2].textContent = dev[2];
			clone.children[0].children[3].textContent = dev[3];
			clone.classList.remove("invisible");

			devCountThisRow += 1;
		});

		devHolder.remove();
		devBox.remove();
	})
</script>

<div class="w-full mt-20">
	<section class="w-full">
		<h1 class="m-auto text-center text-3xl">Meet the Team</h1>

		<div class="flex w-4/5 justify-center m-auto flex-col" id="rowHolder">
			
		</div>

		<div class="flex justify-evenly w-full mt-12" id="devHolder">
				
		</div>

		<div class="w-full max-w-sm bg-white border border-gray-200 rounded-lg shadow" id="devBox">
			<div class="flex flex-col items-center pb-10">
				<img class="w-24 h-24 mb-3 rounded-full shadow-lg mt-3" src="" alt=":3"/>
				<h5 class="mb-1 text-xl font-medium text-gray-900">Person</h5>
				<span class="text-sm text-gray-500 ">Developer</span>
				<p class="text-sm text-gray-500">Does stuff :3</p>
			</div>
		</div>
	</section>
</div>

<style lang="postcss">


</style>