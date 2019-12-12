<script>
	export let size;
</script>
<div class="{size ? size : 'col'}">
	<slot></slot>
</div>
