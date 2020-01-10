<style lang="scss">

</style>

<script>
	let cats = [
		{ label: 'Address', value: 'SYSPAL, Cockshutt Lane' },
		{ label: 'Telephone', value: '07527564964' }
  ];
  let invite = false;
</script>

<svelte:head>
	<title>Contact</title>
</svelte:head>
  
<form name="wedding-rsvp-v1" method="POST" data-netlify="true">
  <input type="hidden" name="form-name" value="wedding-rsvp-v1">
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
    
  <div class="form-group row">
    <label class="col-4">Attending day ceremony</label> 
    <div class="col-8">
      <div class="custom-control custom-checkbox custom-control-inline">
        <input bind:checked={invite} name="day" id="day" type="checkbox" class="custom-control-input" value={true}> 
        <label for="day" class="custom-control-label"></label>
      </div>
    </div>
  </div>
      <p>Please upload a clear photo of the menu choices for each guest below</p>
      <input type="file" name="myFile">
  
  
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


