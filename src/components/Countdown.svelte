<style>
ul {
	padding-left: 0px;
}

li {
    display: inline-block;
    font-size: 0.9em;
    list-style-type: none;
    padding: 1em;
    text-transform: uppercase;
    text-align: center;
}

li span {
    display: block;
    font-size: 1.4rem;
    color: darkgreen;
}

</style>
<script>

import { onMount } from 'svelte';
onMount(() => {
    const second = 1000,
    minute = second * 60,
    hour = minute * 60,
    day = hour * 24;
    if (document.getElementById('days')){
    let countDown = new Date('August 28, 2021 00:00:00').getTime(),
    
    x = setInterval(function() {

    let now = new Date().getTime(),
    distance = countDown - now;
    
    document.getElementById('days').innerText = Math.floor(distance / (day)),
    document.getElementById('hours').innerText = Math.floor((distance % (day)) / (hour)),
    document.getElementById('minutes').innerText = Math.floor((distance % (hour)) / (minute)),
    document.getElementById('seconds').innerText = Math.floor((distance % (minute)) / second);
    }, second);
    }

   
});

</script>
<div>
    <ul class="text-center">
        <li><span id="days"></span>days</li>
        <li><span id="hours"></span>Hours</li>
        <li><span id="minutes"></span>Minutes</li>
        <li><span id="seconds"></span>Seconds</li>
    </ul>
</div>
