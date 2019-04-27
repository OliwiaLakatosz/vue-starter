<template>
	<div>
		<p >Witaj, {{ username }}!</p>
		<a @click="$emit('logout')">Wyloguj się</a>
		<br>
		<meetings-page>Dodaj nowe spotkanie</meetings-page>
		
	</div>
</template>

<script>
import MeetingsPage from "./meetings/MeetingsPage.vue";

	export default {
		components: { MeetingsPage },
		props: ['username'],
		methods: {
			addNewMeeting(meeting) {
				this.meetings.push("nowe spotkanie");
			}
		}
	}
</script>