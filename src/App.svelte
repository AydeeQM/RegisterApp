<script>
	import Router from 'svelte-spa-router'
	import Login from './pages/Login/index.svelte';
	import Home from './pages/Home/Todo_list.svelte';

	const routes = {
    '/': Login,
    '/home': Home,
	}
</script>

<Router {routes} />
