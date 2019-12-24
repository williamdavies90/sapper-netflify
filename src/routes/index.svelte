<script>
	import { Swipe, SwipeItem } from "svelte-swipe"; // gzipped 3.37 KB
	import Row from '../components/Row.svelte';
	import Col from '../components/Col.svelte';
	import { onMount } from 'svelte';
	let autoplay = false;
	let delay = 2000; //ms
	let showIndicators = true;
	let transitionDuration = 1000; //ms
	//countdown timer
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
<style>
	h1 {
		font-size: 2.8em;
		text-transform: uppercase;
		font-weight: 700;
		margin: 0 0 0.5em 0;
	}
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
	.swipe-holder{
		height: 30vh;
		width: 100%;
	}
	img{
		max-width: 100%;
		height: auto;
  	}
</style>

<svelte:head>
	<title>Lucy &amp; Tim</title>
</svelte:head>
<div class="swipe-holder">
  <Swipe {showIndicators} {autoplay} {delay} {transitionDuration}>
    <SwipeItem>
      <img class="mx-auto d-block img-fluid" src="../tim-and-lucy-mobile.jpg" alt="">
    </SwipeItem>
    <SwipeItem>
      <img class="mx-auto d-block img-fluid" src="../tim-and-lucy2-mobile.jpg" alt="">
    </SwipeItem>
  </Swipe>
</div>
<ul class="text-center">
    <li><span id="days"></span>days</li>
    <li><span id="hours"></span>Hours</li>
    <li><span id="minutes"></span>Minutes</li>
    <li><span id="seconds"></span>Seconds</li>
</ul>
