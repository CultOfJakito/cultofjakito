<script>
	import Header from './components/Header.svelte';
	import '../styles.css';
</script>

<div class="bg-grey-dark text-white">
	<Header />

	<main>
		<slot />
	</main>

</div>
