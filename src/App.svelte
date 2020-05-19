<script>
	import { Route, Router } from 'svelte-routing';

	import Library from './library/Library.svelte';
	import Detail from './detail/Detail.svelte';
	import Create from './create/Create.svelte';
	
	export let url = '';

</script>

<Router {url}>
<main>
	<Route path="/create">
		<Create />
	</Route>
	<Route path="/books/:id" let:params>
		<Detail id={params.id} />
	</Route>
	<Route path="/">
	<Library />
	</Route>
</main>	
</Router>

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