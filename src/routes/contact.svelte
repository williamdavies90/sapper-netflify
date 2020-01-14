<script>
import Icon from 'fa-svelte'
import {
  faMobile,
  faEnvelope
} from "@fortawesome/free-solid-svg-icons";
  import Row from '../components/Row.svelte';
  import Col from '../components/Col.svelte';
</script>
<style lang="scss">
.green {
  color: darkgreen;
}
a {
	text-decoration: underline;
}
</style>
<svelte:head>
	<title>Contact</title>
</svelte:head>
<p>For any further information, to RSVP or to inform us of any dietary requirements please do not hesitate to contact us using the information provided below.</p>
<Row>
  <Col>
    <h3>Bride</h3>
    <p class="green"><Icon icon={faMobile}></Icon> <a href="tel:07850288813">07850288813</a></p>
    <p class="green"><Icon icon={faEnvelope}></Icon> <a href="mailto:lucy.maric@hotmail.co.uk">lucy.maric@hotmail.co.uk</a></p>
  </Col>
  <Col>
    <h3>Groom</h3>
    <p class="green"><Icon class="green" icon={faMobile}></Icon> <a href="tel:07731590280">07731590280</a></p>
    <p class="green"><Icon class="green" icon={faEnvelope}></Icon> <a href="mailto:tgreen0307@hotmail.co.uk">tgreen0307@hotmail.co.uk</a></p>
  </Col>
</Row>

<br>
<br>
<br>
<br>


