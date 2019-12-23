<style lang="scss">

</style>

<script>
	let cats = [
		{ label: 'Address', value: 'SYSPAL, Cockshutt Lane' },
		{ label: 'Telephone', value: '07527564964' }
	];
</script>

<svelte:head>
	<title>Contact</title>
</svelte:head>

{#each cats as cat}
	<p>{cat.label}: {cat.value}</p>
{/each}

<form name="contact" method="POST" data-netlify="true">
  <input type="hidden" name="form-name" value="contact" />
  <p>
    <label>Your Name: <input type="text" name="name" /></label>   
  </p>
  <p>
    <label>Your Email: <input type="email" name="email" /></label>
  </p>
  <p>
    <label>Your Role: <select name="role[]" multiple>
      <option value="leader">Leader</option>
      <option value="follower">Follower</option>
    </select></label>
  </p>
  <p>
    <label>Message: <textarea name="message"></textarea></label>
  </p>
  <p>
    <button type="submit">Send</button>
  </p>
</form>



