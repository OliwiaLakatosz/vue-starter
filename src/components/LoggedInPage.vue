<template>
	<div>
		<p>Zalogowany jako {{ username }}</p>
		<button @click="$emit('logout')">Wyloguj sie</button>
		
		<h1>Spotkania</h1>
		
		<button @click="addNewMeeting()">Dodaj nowe spotkanie</button>
		
		<ol>
  			<li v-for="meeting in meetings" :key="meeting.id">{{ meeting }}</li>
		</ol>
		
	</div>
</template>

<script>
	export default {
		props: ['username'],
		data() {
			return {
				meetings: [
					'MWO',
					'TO',
					'INNE',
				]
			};
		},
		methods: {
			addNewMeeting(meeting) {
				this.meetings.push("nowe spotkanie");
			}
		}
	}
</script>