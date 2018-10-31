<template>
	<div>
		<p> {{title}} {{value}} {{description}}</p>	
	</div>
</template>

<script type="text/javascript">
	export default {
		props: ["value","title", "description"]
	}
</script>