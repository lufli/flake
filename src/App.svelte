<script>
	import Router from 'svelte-spa-router';
	import {link, push, pop, wrap} from 'svelte-spa-router';
	import TopAppBar, {Row, Section, Title} from '@smui/top-app-bar';
	// import AppBar from './components/AppBar.svelte';
	import Home from './routes/Home.svelte';
	import Haha from './routes/Haha.svelte';

	let prominent = false;
	let dense = false;
	let secondaryColor = false;

	const routes = {
		// Exact path
		'/': Home,

		// Wildcard parameter
		'/haha': Haha,
	};
</script>

<body>
	<!-- Navigate with buttons -->
	<TopAppBar variant="static" {prominent} {dense} color={secondaryColor ? 'secondary' : 'primary'}>
        <Row>
          	<Section>
				<!-- <IconButton class="material-icons">menu</IconButton> -->
				<Title>Flex Static</Title>
          	</Section>
			<Section align="end" toolbar>
				<!-- <IconButton class="material-icons" aria-label="Download">file_download</IconButton>
				<IconButton class="material-icons" aria-label="Print this page">print</IconButton>
				<IconButton class="material-icons" aria-label="Bookmark this page">bookmark</IconButton> -->
			</Section>
        </Row>
	</TopAppBar>
	<p class="navigation-buttons">
		<button on:click={() => push('/haha')}>Visit /haha</button>
		<button on:click={() => pop()}>Go back</button>
	</p>
	<Router {routes}/>
</body>