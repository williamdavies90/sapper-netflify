<style>
	.date {
		text-align: center;
	}
</style>

<svelte:head>
	<title>Lucy &amp; Tim</title>
</svelte:head>
<div>
	<Carousel perPage={{800: 1, 500: 1 }}>
		<span class="control" slot="left-control">
			<ChevronLeftIcon />
		</span>
		<div class="slide-content"><img width="640" class="mx-auto d-block img-fluid" src="../tim-and-lucy-mobile.jpg" alt=""></div>
		<div class="slide-content"><img width="640" class="mx-auto d-block img-fluid" src="../tim-and-lucy2-mobile.jpg" alt=""></div>
		<span class="control" slot="right-control">
			<ChevronRightIcon />
		</span>
	</Carousel>
</div>

<h2 class="text-center mt-4 mb-0">June 27th 2020</h2>

<Countdown/>



<script>
	import Row from '../components/Row.svelte';
	import Col from '../components/Col.svelte';
	import Countdown from '../components/Countdown.svelte';
	import Carousel from '@beyonk/svelte-carousel';
	import { ChevronLeftIcon, ChevronRightIcon } from 'svelte-feather-icons';
</script>