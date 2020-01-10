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
  
<form name="wedding-rsvp-v1" method="POST" data-netlify="true">
  <input type="hidden" name="form-name" value="wedding-rsvp-v1">
  <div class="form-group row">
    <label class="col-4 col-form-label">Type of guest</label> 
    <div class="col-8">
      <div class="custom-controls-stacked">
        <div class="custom-control custom-radio">
          <input bind:group={invite} name="type_of_guest" id="type_0" type="radio" required="required" class="custom-control-input" value={1}> 
          <label for="type_0" class="custom-control-label">Day and Evening</label>
        </div>
      </div>
      <div class="custom-controls-stacked">
        <div class="custom-control custom-radio">
          <input bind:group={invite} name="type_of_guest" id="type_1" type="radio" required="required" class="custom-control-input" value={2}> 
          <label for="type_1" class="custom-control-label">Evening only</label>
        </div>
      </div>
    </div>
  </div>
  <div class="form-group row">
    <label for="name" class="col-4 col-form-label">Name</label> 
    <div class="col-8">
      <input id="name" name="name" type="text" class="form-control" required="required">
    </div>
  </div>
  <div class="form-group row">
    <label for="email" class="col-4 col-form-label">Email Address</label> 
    <div class="col-8">
      <input id="email" name="email" type="text" class="form-control" required="required">
    </div>
  </div>
  <div class="form-group row">
    <label class="col-4 col-form-label" for="comment">Comment</label> 
    <div class="col-8">
      <textarea id="comment" name="comment" cols="40" rows="3" class="form-control"></textarea>
    </div>
  </div>
  <input id="start-hidden" name="starter" type="hidden" value="">
    <p>Please fill out one of the below for each guest in your party including yourself</p>
    {#each Array(guests) as _, i}
    {#if invite == 1}
    <div class="form-group row">
      <div class="col-8">
        <div class="custom-controls-stacked">
          <div class="custom-control custom-radio">
            <input id="guests" type="file" name="myFile" multiple>
          </div>
        </div>
      </div>
    </div>
    {/if}
    {#if guests > 1}<hr>{/if}
    <button on:click={addGuest}>Add Guest</button>
    {/each}
  
  <div class="form-group row">
    <div class="offset-4 col-8">
      <button name="submit" type="submit" class="btn btn-primary">Submit</button>
    </div>
  </div>
</form>
<br>
<br>
<br>
<br>


