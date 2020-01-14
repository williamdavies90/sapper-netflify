<script>
	import Row from '../components/Row.svelte';
	import Col from '../components/Col.svelte';
	import Icon from 'fa-svelte'
	import { faInstagram } from "@fortawesome/free-brands-svg-icons";
</script>

<style lang="scss">
header {
	border-bottom: 1px solid lightgray;
	margin-bottom: 1em;
}

@media (min-width: 769px) {
	header {
	border-bottom: none !important;
	}
}
</style>

<header>
	<h1 class="text-center mt-2 mb-2">Lucy & Tim</h1>
</header>
