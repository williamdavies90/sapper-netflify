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
          <input bind:group={invite} name="day_and_evening" id="type_0" type="radio" required="required" class="custom-control-input" value={1}> 
          <label for="type_0" class="custom-control-label">Day and Evening</label>
        </div>
      </div>
      <div class="custom-controls-stacked">
        <div class="custom-control custom-radio">
          <input bind:group={invite} name="evening_only" id="type_1" type="radio" required="required" class="custom-control-input" value={2}> 
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
    <p>Please fill out one of the below for each guest in your party including yourself</p>
    {#each Array(guests) as _, i}
    <div class="form-group row">
      <label for="guest_name" class="col-4 col-form-label">Name</label> 
      <div class="col-8">
        <input id="guest_name" name="guest_name" type="text" class="form-control" required="required">
      </div>
    </div>
    <div class="form-group row">
      <label class="col-4 col-form-label">Attending</label> 
      <div class="col-8">
        <div class="custom-controls-stacked">
          <div class="custom-control custom-radio">
            <input name="attending" id="attending_0" type="radio" required="required" class="custom-control-input" value="accepts"> 
            <label for="attending_0" class="custom-control-label">Joyfully accepts</label>
          </div>
        </div>
        <div class="custom-controls-stacked">
          <div class="custom-control custom-radio">
            <input name="attending" id="attending_1" type="radio" required="required" class="custom-control-input" value="declines"> 
            <label for="attending_1" class="custom-control-label">Regretfully declines</label>
          </div>
        </div>
      </div>
    </div>
    {#if invite == 1}
    <div class="form-group row">
      <label class="col-4 col-form-label">Starter</label> 
      <div class="col-8">
        <div class="custom-controls-stacked">
          <div class="custom-control custom-radio">
            <input name="starter" id="starter_0" type="radio" required="required" class="custom-control-input" value="mushrooms"> 
            <label for="starter_0" class="custom-control-label">Sautéed wild and field mushrooms with garlic parsley and cream sauce served on garlic ciabatta with parmesan shavings</label>
          </div>
        </div>
        <div class="custom-controls-stacked">
          <div class="custom-control custom-radio">
            <input name="starter" id="starter_1" type="radio" required="required" class="custom-control-input" value="haddock"> 
            <label for="starter_1" class="custom-control-label">Smoked Haddock and Chive Fishcake wih dill hollandaise and parmesan shavings</label>
          </div>
        </div>
        <div class="custom-controls-stacked">
          <div class="custom-control custom-radio">
            <input name="starter" id="starter_2" type="radio" required="required" class="custom-control-input" value="chicken and chorizo"> 
            <label for="starter_2" class="custom-control-label">Warm Chicken and Chorizo on a roasted red pepper and spring onion salad</label>
          </div>
        </div>
      </div>
    </div>
    <div class="form-group row">
      <label class="col-4 col-form-label">Main Course</label> 
      <div class="col-8">
        <div class="custom-controls-stacked">
          <div class="custom-control custom-radio">
            <input name="main" id="main_0" type="radio" required="required" class="custom-control-input" value="beef"> 
            <label for="main_0" class="custom-control-label">Tender braised blade of beef with a red wine and shallot jus</label>
          </div>
        </div>
        <div class="custom-controls-stacked">
          <div class="custom-control custom-radio">
            <input name="main" id="main_1" type="radio" required="required" class="custom-control-input" value="chicken"> 
            <label for="main_1" class="custom-control-label">Free range chicken breast with a garlic, red wine and bacon jus</label>
          </div>
        </div>
        <div class="custom-controls-stacked">
          <div class="custom-control custom-radio">
            <input name="main" id="main_2" type="radio" required="required" class="custom-control-input" value="butternut squash"> 
            <label for="main_2" class="custom-control-label">Butternut squash, sage and parmesan risotto</label>
          </div>
        </div>
        <div class="custom-controls-stacked">
          <div class="custom-control custom-radio">
            <input name="main" id="main_3" type="radio" required="required" class="custom-control-input" value="vegetable wellington"> 
            <label for="main_3" class="custom-control-label">Roasted mediterranean vegetable wellington with a tomato and basil sauce</label>
          </div>
        </div>
      </div>
    </div>
    <div class="form-group row">
      <label class="col-4 col-form-label">Dessert</label> 
      <div class="col-8">
        <div class="custom-controls-stacked">
          <div class="custom-control custom-radio">
            <input name="dessert" id="dessert_0" type="radio" required="required" class="custom-control-input" value="crème brûlée"> 
            <label for="dessert_0" class="custom-control-label">Baileys crème brûlée with homemade shortbread biscuit</label>
          </div>
        </div>
        <div class="custom-controls-stacked">
          <div class="custom-control custom-radio">
            <input name="dessert" id="dessert_1" type="radio" required="required" class="custom-control-input" value="chocolate brownie"> 
            <label for="dessert_1" class="custom-control-label">Warm chocolate brownie with chocolate sauce and vanilla ice-cream</label>
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


