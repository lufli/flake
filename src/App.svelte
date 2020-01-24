<script>
	import Router from 'svelte-spa-router'
	import {link, push, pop, wrap} from 'svelte-spa-router'
	import Home from './routes/Home.svelte'
	import Haha from './routes/Haha.svelte'

	const routes = {
		// Exact path
		'/': Home,

		// Wildcard parameter
		'/haha': Haha,
	}
</script>

<body>
	<!-- Navigate with buttons -->
	<p class="navigation-buttons">
		<button on:click={() => push('/haha')}>Visit /haha</button>
		<button on:click={() => pop()}>Go back</button>
	</p>
	<Router {routes}/>
</body>