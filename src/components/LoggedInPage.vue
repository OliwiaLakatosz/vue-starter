<template>
	<div>
		<p>Zalogowany jako {{ username }}</p>
		<button @click="$emit('logout')">Wyloguj sie</button>
	</div>
</template>

<script>
	export default {
		props: ['username']
	}
</script>