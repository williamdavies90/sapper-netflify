<script>
	import Icon from 'fa-svelte'
	import {
		faHome,
		faMapMarkedAlt,
		faBed,
		faGift,
		faEnvelope,
		faRings
	} from "@fortawesome/free-solid-svg-icons";
	// import { faInstagram } from "@fortawesome/free-brands-svg-icons";
	export let segment;
</script>

<style lang="scss">
	nav {
		font-weight: 300;
		padding: 0 1em;
		text-align: center;
		
	}

	ul {
		display: inline-block;
		padding: 0;
	}

	/* clearfix */
	ul::after {
		content: '';
		display: block;
		clear: both;
	}

	li {
		display: block;
		float: left;
	}

	.selected {
		position: relative;
		display: inline-block;
	}

	.selected::after {
		position: absolute;
		content: '';
		width: calc(100% - 1em);
		height: 2px;
		background-color: darkgreen;
		display: block;
		bottom: -1px;
	}

	a {
		text-decoration: none;
		padding: 0.5em;
		display: block;
		text-transform: uppercase;
	}
@media (min-width: 769px) {
	nav {
		border-top: none !important;
		border-bottom: 1px solid lightgray;
		margin-bottom: 1em;
	}
	span.icon {
		display: none !important;
	}
}
@media (max-width: 768px) {
	/*Touch Only*/
	nav {
		background-color: #FFFFFF;
		position: fixed;
		bottom: 0;
		z-index: 999999;
		width: 100%;
		border-top: 1px solid lightgray;
	}
	nav ul {
			width: 100%;
			max-width: 600px;
			margin-bottom: 0px !important;
	}
	li {
		width: 25%;
		color: gray !important;
	}
	li a {
		font-size: 22px;
		line-height: 16px; 
		padding-bottom: 5px;
	}
	li a span {
			font-size: 11px !important;
		}
	li a span.icon {
			font-size: 22px !important;
			line-height: 16px !important; 
		}
	a:hover, .selected {
		color: darkgreen;
	}
	a:hover:after, .selected:after {
		background-color: inherit;
	}
}
</style>

<nav>
	<ul>
		<li><a class:selected='{segment === undefined}' href='.'><span class="icon"><Icon class="test mx-auto d-block" icon={faHome}></Icon></span><span>home</span></a></li>
		<li><a rel=prefetch class:selected='{segment === "location"}' href='location'><span class="icon"><Icon class="test mx-auto d-block" icon={faMapMarkedAlt}></Icon></span><span>venue</span></a></li>
		<li><a class:selected='{segment === "hotels"}' href='hotels'><span class="icon"><Icon class="test mx-auto d-block" icon={faBed}></Icon></span><span>hotels</span></a></li>
		<!-- <li><a class:selected='{segment === "gifts"}' href='gifts'><span class="icon"><Icon class="test mx-auto d-block" icon={faGift}></Icon></span><span>gifts</span></a></li> -->
		<li><a class:selected='{segment === "contact"}' href="contact"><span class="icon"><Icon class="test mx-auto d-block" icon={faEnvelope}></Icon></span><span>contact</span></a></li>
		<!-- <li><a class:selected='{segment === "contact"}' href='contact'><Icon class="mx-auto d-block" icon={faEnvelope}></Icon><span>rsvp</span></a></li> -->
		<!-- <li><a class:selected='{segment === "contact"}' href='contact'><Icon class="mx-auto d-block" icon={faMusic}></Icon><span>music</span></a></li> -->
		<!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen -->
		<!-- <li><a rel=prefetch class:selected='{segment === "blog"}' href='blog'>blog</a></li> -->
	</ul>
</nav>
