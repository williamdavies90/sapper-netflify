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
@media (max-width: 767px) {
	header {
	position: fixed;
	top: 0;
	width: 100%;
	background: #FFFFFF;
	border-top: 3px solid darkgreen;
	}
}

</style>

<header>
	<h1 class="text-center mt-2 mb-2">Lucy & Tim</h1>
</header>
