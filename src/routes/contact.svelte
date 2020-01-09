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
  <form name="contact3" method="POST" data-netlify="true">
  <input type="hidden" name="form-name" value="contact3">
  <p><input type="radio" name="menu" value={1} bind:group={invite}> Day and Evening</p>
  <p><input type="radio" name="evening" value={2} bind:group={invite}>Evening</p>
  <div class="d-none"><fieldset><p><label>Name: <input type="text" name="name0"></label></p> <p><label>Attending: <input type="text" name="attending0"></label></p> <p><label>Starter: <input type="text" name="starter0"></label></p> <p><label>Main Course: <input type="text" name="main_course0"></label></p> <p><label>Dessert <input type="text" name="Dessert0"></label></p></fieldset><fieldset><p><label>Name: <input type="text" name="name1"></label></p> <p><label>Attending: <input type="text" name="attending1"></label></p> <p><label>Starter: <input type="text" name="starter1"></label></p> <p><label>Main Course: <input type="text" name="main_course1"></label></p> <p><label>Dessert <input type="text" name="Dessert1"></label></p></fieldset><fieldset><p><label>Name: <input type="text" name="name2"></label></p> <p><label>Attending: <input type="text" name="attending2"></label></p> <p><label>Starter: <input type="text" name="starter2"></label></p> <p><label>Main Course: <input type="text" name="main_course2"></label></p> <p><label>Dessert <input type="text" name="Dessert2"></label></p></fieldset><fieldset><p><label>Name: <input type="text" name="name3"></label></p> <p><label>Attending: <input type="text" name="attending3"></label></p> <p><label>Starter: <input type="text" name="starter3"></label></p> <p><label>Main Course: <input type="text" name="main_course3"></label></p> <p><label>Dessert <input type="text" name="Dessert3"></label></p></fieldset><fieldset><p><label>Name: <input type="text" name="name4"></label></p> <p><label>Attending: <input type="text" name="attending4"></label></p> <p><label>Starter: <input type="text" name="starter4"></label></p> <p><label>Main Course: <input type="text" name="main_course4"></label></p> <p><label>Dessert <input type="text" name="Dessert4"></label></p></fieldset><fieldset><p><label>Name: <input type="text" name="name5"></label></p> <p><label>Attending: <input type="text" name="attending5"></label></p> <p><label>Starter: <input type="text" name="starter5"></label></p> <p><label>Main Course: <input type="text" name="main_course5"></label></p> <p><label>Dessert <input type="text" name="Dessert5"></label></p></fieldset><fieldset><p><label>Name: <input type="text" name="name6"></label></p> <p><label>Attending: <input type="text" name="attending6"></label></p> <p><label>Starter: <input type="text" name="starter6"></label></p> <p><label>Main Course: <input type="text" name="main_course6"></label></p> <p><label>Dessert <input type="text" name="Dessert6"></label></p></fieldset><fieldset><p><label>Name: <input type="text" name="name7"></label></p> <p><label>Attending: <input type="text" name="attending7"></label></p> <p><label>Starter: <input type="text" name="starter7"></label></p> <p><label>Main Course: <input type="text" name="main_course7"></label></p> <p><label>Dessert <input type="text" name="Dessert7"></label></p></fieldset><fieldset><p><label>Name: <input type="text" name="name8"></label></p> <p><label>Attending: <input type="text" name="attending8"></label></p> <p><label>Starter: <input type="text" name="starter8"></label></p> <p><label>Main Course: <input type="text" name="main_course8"></label></p> <p><label>Dessert <input type="text" name="Dessert8"></label></p></fieldset><fieldset><p><label>Name: <input type="text" name="name9"></label></p> <p><label>Attending: <input type="text" name="attending9"></label></p> <p><label>Starter: <input type="text" name="starter9"></label></p> <p><label>Main Course: <input type="text" name="main_course9"></label></p> <p><label>Dessert <input type="text" name="Dessert9"></label></p></fieldset></div>
  {#if invite == 1}    
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
  
  {/if}
  </form>
  



