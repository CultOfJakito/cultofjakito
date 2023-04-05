<script>
	import { page } from '$app/stores';

	import github from '$lib/images/github-mark-white.svg'
	import youtube from '$lib/images/youtube.svg'

	import { onMount } from 'svelte';

	onMount(() => {
		document.getElementById("blocker")?.remove();
	});
</script>

<style>
	.blocker {
		background-image: url("https://i.redd.it/r65eufx731061.jpg");
  		height: 100%;
		width: 100%;
  		background-position: center;
  		background-repeat: no-repeat;
  		background-size: cover;
		position: absolute;
	}
</style>

<body>
	<img alt="" class="blocker" id="blocker">
</body>


<header class="w-full pt-3">
	<navbar class="w-full flex flex-row items-center justify-evenly ">
		<ul class="w-full flex flex-row items-center justify-evenly">
			<li class="inline" aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/">Home</a>
			</li>
			<li class="inline" aria-current={$page.url.pathname === '/about' ? 'page' : undefined}>
				<a href="/about">About</a>
			</li>
			<li class="inline" aria-current={$page.url.pathname === '/projects' ? 'page' : undefined}>
				<a href="/projects">Projects</a>
			</li>
			<li class="inline" aria-current={$page.url.pathname === '/events' ? 'page' : undefined}>
				<a href="/events">Events</a>
			</li>
		</ul>
		<ul class="w-1/6 flex flex-row items-center justify-start">
			<li class="inline mr-4"><a href="https://github.com/CultOfJakito"><img class="h-9 w-9 p-1 hover:p-0 transition-all" src={github} alt=""></a></li>
			<li class="inline"><a href="https://www.youtube.com/channel/UCU531rHxXbIcDG4u_K_QbEw"><img class="h-min w-9 p-1 hover:p-0 transition-all" src={youtube} alt=""></a></li>
		</ul>
	</navbar>
</header>

