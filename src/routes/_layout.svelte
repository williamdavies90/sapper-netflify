<script>
	import Header from '../components/Header.svelte';
	import Nav from '../components/Nav.svelte';

	export let segment;
</script>
<Header/>
<Nav {segment}/>
<main class="container">
	<slot></slot>
</main>