<style lang="scss">

</style>

<script>
	let cats = [
		{ label: 'Address', value: 'SYSPAL, Cockshutt Lane' },
		{ label: 'Telephone', value: '07527564964' }
  ];
  let invite = 0;
  let guests = 1;
  function addGuest(event) {
    event.preventDefault();
    guests++;
  }
</script>

<svelte:head>
	<title>Contact</title>
</svelte:head>

{#each cats as cat}
	<p>{cat.label}: {cat.value}</p>
{/each}

  <p><input type="radio" name="menu" value={1} bind:group={invite}> Day and Evening</p>
  <p><input type="radio" name="evening" value={2} bind:group={invite}>Evening</p>
  {#if invite == 1}
  day
  <form name="rsvp-day" method="POST" data-netlify="true">
    <input type="hidden" name="form-name" value="contact" />
    {#each Array(guests) as _, i}
    <fieldset>
      <p><label>Name: <input type="text" name="name{i}" /></label></p>
      <p><label>Attending: <input type="text" name="attending{i}" /></label></p>
      <p><label>Starter: <input type="text" name="starter{i}" /></label></p>
      <p><label>Main Course: <input type="text" name="main_course{i}" /></label></p>
      <p><label>Dessert <input type="text" name="Dessert{i}" /></label></p>
    </fieldset>
    {/each}
    <p>
      <button on:click={addGuest}>Add Guest</button>
    </p>
    <p>
      <label>Your Email: <input type="email" name="email" /></label>
    </p>
    <p>
      <label>Message: <textarea name="message"></textarea></label>
    </p>
    <p>
      <button type="submit">Send</button>
    </p>
  </form>
  {/if}
  {#if invite == 2}
  evening
	 <form name="contact" method="POST" data-netlify="true">
    <input type="hidden" name="form-name" value="contact" />
    <p>
      <label>Your Name: <input type="text" name="name" /></label>   
    </p>
    <p>
      <label>Your Email: <input type="email" name="email" /></label>
    </p>
    
    <p>
      <label>Message: <textarea name="message"></textarea></label>
    </p>
    <p>
      <button type="submit">Send</button>
    </p>
  </form>
  {/if}
  



