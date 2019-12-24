<script>
	import Row from '../components/Row.svelte';
	import Col from '../components/Col.svelte';
	import { onMount } from 'svelte';
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
		font-size: 0.5em;
		list-style-type: none;
		padding: 1em;
		text-transform: uppercase;
		text-align: center;
	}

	li span {
		display: block;
		font-size: 1.5rem;
	}
</style>

<svelte:head>
	<title>Sapper project template</title>
	<script src="https://identity.netlify.com/v1/netlify-identity-widget.js"></script>
</svelte:head>

<Row>
<img class="d-block mx-auto img-fluid" src="../tim-and-lucy-mobile.jpg" alt="The Happy Couple">
<div class="clearfix"></div>
</Row>
<ul class="text-center">
    <li><span id="days"></span>days</li>
    <li><span id="hours"></span>Hours</li>
    <li><span id="minutes"></span>Minutes</li>
    <li><span id="seconds"></span>Seconds</li>
</ul>
