<script>
	import Icon from 'fa-svelte'
	import {
		faHome,
		faMap,
		faBed,
		faGift,
		faEnvelope
	} from "@fortawesome/free-solid-svg-icons";
	// import { faInstagram } from "@fortawesome/free-brands-svg-icons";
	export let segment;
</script>

<style lang="scss">
	nav {
		border-bottom: 1px solid lightgray;
		font-weight: 300;
		padding: 0 1em;
		text-align: center;
		margin-bottom: 1em;
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
	}
	span.icon {
		display: none !important;
	}
}
@media (max-width: 768px) {
	/*Touch Only*/
	nav {
		position: fixed;
		bottom: 0;
		z-index: 999999;
		width: 100%;
		border-top: 1px solid lightgray;
		ul {
			width: 100%;
			max-width: 600px;
			margin-bottom: 0px;
			li {
				width: 20%;
				color: gray !important;
				a {
					font-size: 22px;
					line-height: 16px; 
					padding-bottom: 5px;
					span {
						font-size: 12px !important;
					}
				}
				a:hover, .selected {
					color: darkgreen;
					&:after {
						background-color: inherit;
					}
				}
			}	
		}
	}
}
</style>

<nav>
	<ul>
		<li><a class:selected='{segment === undefined}' href='.'><span class="icon"><Icon class="test mx-auto d-block" icon={faHome}></Icon></span><span>home</span></a></li>
		<li><a rel=prefetch class:selected='{segment === "location"}' href='location'><span class="icon"><Icon class="test mx-auto d-block" icon={faMap}></Icon></span><span>venue</span></a></li>
		<li><a class:selected='{segment === "hotels"}' href='hotels'><span class="icon"><Icon class="test mx-auto d-block" icon={faBed}></Icon></span><span>hotels</span></a></li>
		<li><a class:selected='{segment === "gifts"}' href='gifts'><span class="icon"><Icon class="test mx-auto d-block" icon={faGift}></Icon></span><span>gifts</span></a></li>
		<li><a class:selected='{segment === "contact"}' href="contact"><span class="icon"><Icon class="test mx-auto d-block" icon={faEnvelope}></Icon></span><span>contact</span></a></li>
		<!-- <li><a class:selected='{segment === "contact"}' href='contact'><Icon class="mx-auto d-block" icon={faEnvelope}></Icon><span>rsvp</span></a></li> -->
		<!-- <li><a class:selected='{segment === "contact"}' href='contact'><Icon class="mx-auto d-block" icon={faMusic}></Icon><span>music</span></a></li> -->
		<!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen -->
		<!-- <li><a rel=prefetch class:selected='{segment === "blog"}' href='blog'>blog</a></li> -->
	</ul>
</nav>
