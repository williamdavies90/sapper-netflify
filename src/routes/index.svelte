
<style>
	ul {
		padding-left: 0px;
	}

	li {
		display: inline-block;
		font-size: 1em;
		list-style-type: none;
		padding: 1em;
		text-transform: uppercase;
		text-align: center;
	}

	li span {
		display: block;
		font-size: 1.5rem;
	}
	img{
		max-width: 100%;
		height: auto;
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

<ul class="text-center">
    <li><span id="days"></span>days</li>
    <li><span id="hours"></span>Hours</li>
    <li><span id="minutes"></span>Minutes</li>
    <li><span id="seconds"></span>Seconds</li>
</ul>
<script>
	
	import Row from '../components/Row.svelte';
	import Col from '../components/Col.svelte';
	import { onMount } from 'svelte';
	import Carousel from '@beyonk/svelte-carousel';
	import { ChevronLeftIcon, ChevronRightIcon } from 'svelte-feather-icons';
	
	onMount(() => {
		const second = 1000,
		minute = second * 60,
		hour = minute * 60,
		day = hour * 24;

		let countDown = new Date('June 27, 2020 00:00:00').getTime(),
		x = setInterval(function() {

		let now = new Date().getTime(),
		distance = countDown - now;

		document.getElementById('days').innerText = Math.floor(distance / (day)),
		document.getElementById('hours').innerText = Math.floor((distance % (day)) / (hour)),
		document.getElementById('minutes').innerText = Math.floor((distance % (hour)) / (minute)),
		document.getElementById('seconds').innerText = Math.floor((distance % (minute)) / second);
		}, second);
	});
	
</script>