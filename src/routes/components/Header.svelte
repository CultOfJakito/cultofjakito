<script>
	import { page } from '$app/stores';
</script>

<header class="w-full">
	<nav class="w-full flex flex-row align-middle items-center justify-center">
		<ul>
			<li class="inline" aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/">Home</a>
			</li>
			<li class="inline" aria-current={$page.url.pathname === '/about' ? 'page' : undefined}>
				<a href="/about">About</a>
			</li>
		</ul>
	</nav>
</header>

