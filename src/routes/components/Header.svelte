<script>
	import { page } from '$app/stores';

	import github from '$lib/images/github-mark-white.svg'
	import youtube from '$lib/images/youtube.svg'
</script>

<header class="w-full pt-3">
	<navbar class="w-full flex flex-row items-center justify-evenly ">
		<ul class="w-full flex flex-row items-center justify-evenly">
			<li class="inline" aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/">Home</a>
			</li>
			<li class="inline" aria-current={$page.url.pathname === '/about' ? 'page' : undefined}>
				<a href="/about">About</a>
			</li>
			<li class="inline" aria-current={$page.url.pathname === '/about' ? 'page' : undefined}>
				<a href="/about">Projects</a>
			</li>
			<li class="inline" aria-current={$page.url.pathname === '/about' ? 'page' : undefined}>
				<a href="/about">Events</a>
			</li>
		</ul>
		<ul class="w-1/6 flex flex-row items-center justify-start">
			<li class="inline mr-4"><a href="https://github.com/CultOfJakito"><img class="h-8 w-8" src={github} alt=""></a></li>
			<li class="inline"><a href="https://www.youtube.com/channel/UCU531rHxXbIcDG4u_K_QbEw"><img class="h-min w-8" src={youtube} alt=""></a></li>
		</ul>
	</navbar>
</header>

