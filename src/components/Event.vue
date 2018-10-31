<template v-if="posts && posts.length > 0" >
	<div>
		<div v-for="post of posts">
			<h1>{{post.title}}</h1>
			<button @click="$emit('enlarge-test', 0.1)">Enlarge</button>
			<p>{{post.description}}</p>
		</div>	
	</div>
	
</template>

<script type="text/javascript">
	export	default {
		props: ["posts"],
	}
</script>